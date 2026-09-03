Co zmienia się z wydania na wydanie – opisane z perspektywy aplikacji, nie
jej wnętrza. Kto chce wiedzieć, *z czego* jest zbudowana, znajdzie to w
[LIZENZEN.md](LIZENZEN.md); tutaj stoi to, co zmienia się dla pracy z nią.

Numeracja stosuje zwykły sposób liczenia: **pierwsza** liczba zmienia się,
gdy coś nie działa już tak jak dotychczas, **druga** przy nowych
możliwościach, **trzecia** przy poprawkach błędów.

---

## 0.10.50-alpha.20260903 – 3 września 2026

- Powtarzające się znaki firmowe w plikach PDF są oczyszczane spójnie, także
  gdy rozpoznawanie tekstu odczytuje napis na jednej stronie inaczej albo
  całkiem pomija okrągły sygnet. Wyraźne odznaczenie w podglądzie pozostaje
  przy tym wiążące i nie może zostać zniesione przez żadne późniejsze
  dociągnięcie.
- Ceny bez waluty w zeskanowanych tabelach są w pełni zaciemniane także
  wtedy, gdy nagłówek tabeli i wartości tkwią w różnych nakładających się
  obrazach PDF. Ilości, godziny, wagi i procenty pozostają nienaruszone;
  odległe od siebie liczby nie są już przypadkowo łączone w kwotę.
- Wyszukiwanie podpisów obejmuje teraz też udokumentowane słabe niebieskie
  napisy i wąskie czerwone skróty sygnatur. Wykresy punktowe, krzywe
  pomiarowe, pieczątki, logo i szerokie czerwone oznaczenia redakcyjne
  pozostają wyłączone z tego ciasnego dociągnięcia.
- Zaciemnienia w obróconych, odbitych lustrzanie, ściętych lub przyciętych
  obrazach PDF trafiają teraz rzeczywisty wielokąt obrazu. Techniczne role
  w pozycjach świadczeń, dane rzeczowe pojazdów i opon oraz techniczna
  „kompensacja” są jednocześnie ciaśniej odgraniczone od fałszywych trafień;
  wyraźnie opisane role kontaktowe i numery telefonu pozostają chronione.
- Kontrola wzrokowa przed zapisem PDF nie zamraża już okna: przy dużych
  dokumentach z wieloma miejscami znalezienia stało ono dotychczas kilka
  sekund bez odpowiedzi; teraz wskazówka pokazuje, że trwa sprawdzanie, a
  okno rysuje dalej.
- Przywracanie wartości z obrazu w edytorze poprawek czyta każdy obraz
  oryginału przez rozpoznawanie tekstu już tylko raz; dotychczas
  uruchamiało się ono ponownie przy każdym kolejnym przywróceniu dla tych
  samych obrazów.
- Doładowanie poziomu Wysokiego i modelu podpisów potrzebuje teraz ledwie
  pamięci roboczej: pakiet 596 MB był dotychczas w całości trzymany w
  pamięci, sprawdzany i tam rozpakowywany – ponad gigabajt szczytowo w
  działającym programie, na komputerach z 8 GB moment, w którym wszystko
  zaczynało się zacinać. Teraz płynie blokowo na dysk i tam jest sprawdzany
  i rozpakowywany.
- Wyszukiwanie w edytorze poprawek nie zamraża już dużych plików PDF:
  pierwsza litera w polu wyszukiwania wczytywała dotychczas wszystkie
  strony naraz – przy 200 stronach okno stało dwie sekundy, a po każdym
  zaciemnieniu jeszcze raz. Strony są teraz czytane porcjami; do tego czasu
  w liczniku stoi „Wczytywanie …”, wynik jest ten sam.
- Zrasteryzowane strony PDF – po rozpoznawaniu tekstu lub gdy tekstu nie
  dało się czysto usunąć – są zapisywane wyraźnie mniejsze i bez utraty
  obrazu: zamiast zawsze jako JPEG każda strona jest też kodowana
  bezstratnie, a mniejsza wersja trafia do pliku. Oczyszczony skan kurczy
  się tak z 248 do 48 KB, dokument ćwiczeniowy z rozpoznawaniem tekstu z 913
  do 702 KB; tekst pozostaje idealnie ostry.
- Doładowane modele (poziom Wysoki, podpisy, twarze, drugie rozpoznawanie
  tekstu) są po dziesięciu minutach bez oczyszczania z powrotem zwalniane z
  pamięci roboczej. Dotychczas pozostawały wczytane aż do końca programu –
  kto raz użył wyszukiwania podpisów i poziomu Wysokiego, trzymał trwale
  ponad dwa gigabajty. Następny przebieg wczytuje je z powrotem w jedną do
  dwóch sekund; wiersz stanu o tym informuje.
- PowerPoint: nazwy rodzajowe układów slajdów i wzorców slajdów („Pusty”,
  „Slajd tytułowy”) nie są już zastępowane jako dana. „Pusty” to też
  miejscowość i było błędnie zaciemniane w każdej niemieckiej i angielskiej
  prezentacji; oczyszczane są teraz tylko ręcznie nadane nazwy samych
  slajdów.
- W plikach PDF wygładzanie wierszy nie wciąga już nagłówka następnego
  wiersza do trafienia: numer następnego punktu listy za datą liczył się
  jako numer telefonu, nagłówek pola jak „Kod identyfikacyjny” czy „Numer
  zamówienia” za liczbą jako kod pocztowy z miejscowością, a wiersz
  miejscowości pod adresem podwajał miejscowość. Właściwe, krótsze
  znalezisko było przez to wypierane. Na 132 plikach PDF korpusu z 24
  dodatkowych znalezisk wygładzania pozostają dwa prawdziwe; w korpusie
  praktycznym fałszywe alarmy spadają z 29 do 21 przy tej samej stopie
  trafień.
- „Przeszukaj i zaciemnij folder PDF” w edytorze poprawek nie blokuje już
  okna: przebieg działa w tle, postęp i przycisk anulowania reagują, a
  menu czy zakładki nie dają się już obsługiwać w środku na wpół gotowego
  pliku.
- Zeskanowane strony z miejscami znalezienia są przy zaciemnianiu
  zapisywane na nowo już tylko raz zamiast dwa razy: dotychczas program
  wypełniał pola miejsc znalezienia i pola uzasadnień w dwóch przebiegach,
  a drugi kompresował właśnie na nowo zapisany obraz skanu jeszcze raz. To
  oszczędza czas przy dużych skanach i utratę jakości obrazu.
- Przewijanie, powiększanie i miniatury w edytorze poprawek reagują
  szybciej: każda wyrenderowana strona przechodziła dotychczas jako PNG
  przez kompresję i od razu z powrotem, tylko po to, żeby zostać
  wyświetloną – przy ekranach o wysokiej rozdzielczości około jednej
  dziesiątej sekundy na stronę. Obraz przychodzi teraz bezpośrednio,
  piksel po pikselu ten sam.
- Kontrola wzrokowa przed zapisem PDF („próba wyjściowa”) jest około
  trzykrotnie szybsza, przy tym samym wyniku.
- Okno główne stoi jeszcze raz o około jedną czwartą sekundy wcześniej:
  sprawdzenie, czy rozpoznawanie tekstu jest gotowe na tym komputerze,
  odbywało się przy budowie okna – na Macu wraz z próbnym zapytaniem do
  rozpoznawania systemowego – a strona ustawień modułów dodatkowych
  odpytywała przy tym stan wszystkich 48 języków. Oba dzieją się teraz w
  tle, względnie dopiero wtedy, gdy lista języków jest naprawdę otwierana;
  do tego czasu stoi „Sprawdzanie rozpoznawania tekstu …”.
- Po wyszukiwaniu podpisów program zajmuje około 300 MB mniej pamięci
  roboczej: model rozpoznawania leżał do tej pory podwójnie w pamięci –
  raz do sprawdzenia swojej autentyczności, raz do liczenia. Jest nadal
  sprawdzany, tylko bez drugiej kopii.
- Rozpoznawanie tekstu w plikach PDF stało się wyraźnie szybsze: dla
  każdego nagłówka pola na stronie („Data urodzenia:”, „Numer podatkowy:”)
  wysyłana była dotychczas dla każdego rodzaju danej osobna próba przez
  rozpoznawanie – na każdej stronie od nowa, nawet gdy ten sam nagłówek
  stał już dziesięć stron wcześniej. Odpowiedź jest teraz zapamiętywana;
  dwustronicowy przedmiar robót stawiał tak 324 pytania, teraz tylko różne.
  Znaleziska są te same.
- Duże tabele są znów oczyszczane w sekundy zamiast minuty: w trybie
  anonimizującym – domyślnym – dopasowywanie już znanych wartości do
  każdej kolejnej komórki stawało się wolniejsze, ponieważ pamięć
  podręczna była przy każdym trafieniu odrzucana i budowana na nowo. 5000
  komórek potrzebowało na to około 18 sekund, teraz pół sekundy; wynik
  jest znak w znak ten sam.
- Okno główne pojawia się jeszcze raz wyraźnie szybciej: lista krajów w
  ustawieniach wciągała przy budowie okna całą bibliotekę rozpoznawania na
  pierwszy plan – około 0,7 sekundy na Macu, na Windows odpowiednio
  więcej – mimo że potrzebne są do tego tylko nazwy krajów. Lista pochodzi
  teraz z lekkiego katalogu; biblioteka wczytuje się zgodnie z planem w
  tle, podczas gdy okno już stoi. Dotyczy to też po każdej zmianie języka
  lub wyglądu, która ponownie uruchamia program.
- Laboratorium dokumentów przeprowadza teraz przycięte nagłówki pól,
  lokalne cienie wartości i silne przycięcia skanów w pełni przez
  kontenery PDF, DOCX i ODT. Macierz obejmuje 680 plików z 40 rodzin
  dokumentów i 17 osi kontenerowych. Maskuro usuwa w nowych oraz pełnych
  profilach podstawowych i cechowych wszystkie wartości docelowe, bez
  zmierzonego fałszywego alarmu, uszkodzonej wartości zachowania czy
  przerwania.

- Wielokrotnie używane skany są teraz sprawdzane i oczyszczane przez każde
  widoczne umieszczenie: laboratorium dokumentów dzieli ten sam obiekt
  obrazu na różne strony, rozmiary i położenia obrotu w PDF i odwołuje się
  wielokrotnie do tego samego fragmentu obrazu w DOCX i ODT. Techniczne
  nazwy ramek ODT jak „Skan formularza mały poziomy” nie liczą się już jako
  osoba; wolne nazwiska i miejscowości o podobnym początku pozostają
  chronione. Ogólne przypuszczenie formularza z końcowego przebiegu strony
  PDF nie może już na już niezależnie odczytanej powierzchni obrazu tworzyć
  dużego błędnego znalezienia adresu. 120 nowych kontenerów osiąga w
  profilu podstawowym i cechowym wszystkie odpowiednio 813 i 840 wartości
  docelowych bez fałszywego alarmu, naruszenia zachowania czy przerwania;
  pełny odbiór cechowy 800 plików potwierdza 5600/5600.

- Niemieckie laboratorium OCR obejmuje teraz 560 skanów z 40 rodzin
  dokumentów. Nowe warianty przycinają nagłówek pola i marginesy strony
  lub kładą cień bezpośrednio na wartość. Maskuro chroni przy tym też
  nazwiska, adresy, daty urodzenia, klucze medyczne i opisane numery
  identyfikacyjne z częściowo uszkodzonym opisem. Jednocześnie resztki pól
  formularza, nagłówki urzędowe oraz rzeczowe pojęcia prawne i
  informacyjne nie są już zastępowane jako osoby lub miejscowości. Pełne
  profile podstawowy i cechowy osiągają 3794/3794 oraz 3920/3920 wartości
  docelowych bez zmierzonego fałszywego alarmu czy przerwania.

- Automatyczny wybór obrazów PDF nie usuwa już wielkopowierzchniowych
  zdjęć produktów, etykiet energetycznych i szeregów portretów tylko
  dlatego, że zaczynają się na górnym marginesie strony. Prawdziwe płaskie
  obrazy nagłówka/stopki i nagłówki firmowe zaczynające się przy krawędzi
  kartki nadal odpadają. W spisach pracowników nazwiska są teraz
  rozpoznawane także wtedy, gdy widoczny tytuł dokumentu istnieje tylko
  jako obraz, z powtarzających się strukturalnie wpisów. Rozpoznawanie nie
  jest już przycięte do dwóch konkretnych słów roli i skrótu „DW”: od
  jednej do czterech złamanych ról oraz „Wewnętrzny”, „Numer wewnętrzny”,
  „Ext.” i „Extension” są wnioskowane z wspólnej budowy. Role i nagłówki
  sekcji pozostają nienaruszone, nawet gdy model językowy po rozwiązaniu
  nakładania zostawia tylko przymiotnik roli. Poziome siatki ról nie liczą
  się już błędnie jako kolumny nazwisk. Jeśli OCR strony skleja kilka kart
  w jedno ekstremalnie szerokie słowo pisane wielkimi literami wewnątrz,
  ciasne lokalne kontrspojrzenie rozdziela rzeczywiste pola słów; dzięki
  temu nie pozostaje ani pojedyncze nazwisko, ani szeroki błędny pas.
  Powtarzające się wielowierszowe logo firmowe są zaciemniane na podstawie
  już potwierdzonego identycznego wzorca pikselowego także na stronach bez
  użytecznego tekstu OCR i przy odchyleniu położenia do dwóch pikseli;
  krótsze lokalne drugie odczyty OCR nie mogą przy tym już uzupełniać
  większego obszaru nagłówka o wymyślone nazwisko. Numery stron przed
  nagłówkiem firmowym nie należą już do nazwy organizacji, prawdziwe nazwy
  marek zaczynające się cyfrą pozostają chronione. Kilka zmierzonych słów
  produktowych, fachowych i formularzowych nie jest już proponowanych jako
  osoby.

- Wyszukiwanie podpisów działa w plikach PDF dopiero po oczyszczeniu
  obrazu OCR, odwiedza też strony bez zwykłego trafienia tekstowego i
  poprawnie przelicza pola znalezienia obróconych stron z powrotem do
  przestrzeni dokumentu. Gęste zdjęcia produktów nie są już zaciemniane
  jako podpis. Nad wyraźnie opisanymi polami sygnatury ciasne rozwiązanie
  rezerwowe kreski zamyka cienkie luki modelu; puste linie z wydrukowaną
  wcześniej datą go nie wywołują. Czyste skany wyłącznie z trafieniami
  OCR/podpisów nie przerywają się już na tym etapie z powodu dopiero w
  gałęzi tekstowej wczytanego zaciemniacza obrazu.

- Wiele jednocześnie otwartych dokumentów pozostaje rozróżnialnych w
  edytorze poprawek: zakładki nie kurczą się już do samego wielokropka, a
  przycisk listy po prawej pokazuje wszystkie pełne nazwy plików jedna pod
  drugą. Zakładki dają się przesuwać przez przeciąganie i zabierać z tej
  samej listy swoim krzyżykiem co w oknie głównym; niezapisana praca jest
  przy tym nadal najpierw wyjaśniana. Kliknięcie prawym przyciskiem
  oferuje ponadto „Zamknij”, „Zamknij pozostałe zakładki” i „Zamknij
  zakładki po prawej”.

- Krótkotrwała blokada Windows przez skaner antywirusowy lub indeks
  wyszukiwania nie powoduje już, że gotowo wczytany folder modelu
  językowego lub słownika kończy się przy końcowym wstawianiu błędem
  „Odmowa dostępu”. Maskuro próbuje teraz tej ostatniej zmiany folderu
  ponownie przez krótki czas.

- Niemieckie laboratorium dokumentów sprawdza kontenery teraz też ze
  zmiennym obrotem stron PDF, niezależnie obróconymi obrazami PDF oraz
  skalowanymi i przyciętymi obrazami tabel w DOCX i ODT. Wartości pól w
  widocznie obróconych obrazach są znów w pełni rozpoznawane, techniczne
  oznaczenia kolumn nie są już zastępowane jako miejscowości, a nazwiska
  o wspólnym nazwisku rodowym nie są już rozkładane przez dopasowanie
  spójności na podwójne trafienia częściowe. Podwojona do 320 plików
  macierz osiąga przy dołączonym rozpoznawaniu dat, kwot i danych
  medycznych 2240/2240 wartości docelowych bez zmierzonego fałszywego
  alarmu czy przerwania.

- Wielostronicowe PDF-y obrazowe, mieszane PDF-y tekstowo-obrazowe i skany
  osadzone w DOCX lub ODT są teraz sprawdzane w osobnym laboratorium 160
  plików przez wszystkie 40 niemieckich rodzin dokumentów. Techniczne
  nazwy ramek ODT i opisane kody urządzeń nie są już zastępowane jako
  miejscowości; prawdziwe nazwiska, miejscowości i adresy w tych samych
  strukturach pozostają chronione. Przy włączonym rozpoznawaniu medycznym
  lub finansowym bezpośrednio następujące dawkowanie lub interwał
  płatności są ponadto w pełni usuwane. Przebiegi kontenerowe, podstawowe
  tekstowe, cechowe tekstowe i cechowe OCR osiągają razem swoje pełne
  stany bez zmierzonego fałszywego alarmu czy przerwania.

- Sprawdzenie bezpieczeństwa przed zapisem pokazuje teraz zauważalne
  miejsca PDF jako pojedynczo wybieralną listę. „Sprawdź w edytorze”
  otwiera dokładnie wybraną stronę i zaznacza obszar; nakładające się
  trafienia częściowe w tym samym miejscu pojawiają się już tylko raz.
  Nowe teksty obsługi są w pełni dostępne we wszystkich 17 przetłumaczonych
  językach interfejsu.

- Pliki Markdown zachowują przy zastępowaniu swoją składnię odsyłaczy,
  wyróżnień i przypisów. Maskuro czyta do tego wersję o tej samej długości
  znaków bez znaczników Markdown; podkreślenia w adresach e-mail, gwiazdki
  rachunkowe i zwykłe odsyłacze bez danej osobowej pozostają nienaruszone.

- Kilka odręcznych wpisów na tej samej stronie PDF jest teraz szukanych w
  do trzech przebiegach. Już znalezione pociągnięcia są ukrywane tylko w
  obrazie roboczym, żeby nie wypierały już słabszych podpisów; na
  obróconych stronach powierzchnie zaciemnienia lądują znów na widocznym
  miejscu znalezienia. Wypełnienia obrazu z wcześniejszych faz
  bezpieczeństwa pozostają zachowane przy następującym zapisie zwrotnym.

- „Zresetuj wszystkie ustawienia” obejmuje teraz też „Tekst w obrazach”.
  Jeśli moduł OCR nie jest dostępny, przełącznik pozostaje technicznie
  wyłączony, bez błędnego oznaczenia jako odbiegający od stanu wydania.

- Duże fragmenty obrazu na górnym marginesie strony nie liczą się już jako
  nagłówek tylko z powodu swojego położenia. Dzięki temu zachowane
  pozostają zwłaszcza opisy artykułów oparte na obrazach i treści tabel.
  Nowo rozpoznane, dokładne co do typu znaleziska e-mail i formularzy nie
  są ponadto już odfiltrowywane z końcowej kontroli wzrokowej na już
  sprawdzonej powierzchni obrazu.

- Techniczne wiersze pozycji i artykułów w ofertach klimatyzacji i
  elektryki są ciaśniej odróżniane od osób, miejscowości i organizacji.
  Dotyczy to między innymi typów kabli, zasilania AC, numerów pozycji oraz
  kodów produktów wielkimi literami; prawdziwe nazwiska i adresy
  pozostają chronione.

- Sprawdzenie prawdziwych oczyszczonych plików PDF nie myli już
  składników cen jak `1 699,59` z numerami telefonu i nie wycina z pełnej
  daty jak `08.05.2025` żadnej rzekomej danej karty. Nazwiska za formą
  grzecznościową kończą się na złamaniu wiersza zamiast w następującej
  ulicy; nazwy miejscowości w nazwach plików załączników są ograniczane do
  rzeczywistej miejscowości. Kolory pojazdów, techniczne wartości statusu,
  oznaczenia branży i formy prawne produktów również pozostają zachowane.
  Uszkodzone odczyty zastępników jak `|PLLZ` nie są przy drugim przebiegu
  OCR ponownie traktowane jako dana osobowa.

- Bocznie zapisane obrazy PDF dostają przy końcowej kontroli wzrokowej
  dodatkowe spojrzenie w swoim niezmienionym położeniu obrazu. Może ono
  wyłącznie doczyszczać wartości, które Maskuro na tej samej stronie już
  pewnie rozpoznał. Tak np. mała obrócona pieczątka adresowa jest w pełni
  zakrywana, bez wymyślania nowych słów z nagłówków obrazów lub rysunków
  technicznych jako danych osobowych.

- W tekstach OpenDocument inicjały autora notatki (komentarza) są teraz
  czyszczone razem z autorem. LibreOffice odkłada je obok pełnego nazwiska
  jako własną krótką formę i pokazuje dokładnie ją na marginesie strony;
  dotychczas stało tam dalej „SO”, podczas gdy „Sieglinde Ortner” obok
  było już od dawna zastępnikiem. Czyszczone jest tylko wtedy, gdy autor
  został faktycznie zastąpiony – notatka działu zachowuje swoje
  oznaczenie.

- We włoskich listach biznesowych standardowe zwroty na początku zdania
  nie liczą się już jako nazwisko czy miejscowość: „Restiamo a
  disposizione”, „Rimaniamo”, „Attendiamo”, „Alleghiamo”, „Comunichiamo” i
  „Auguriamo buon lavoro” pozostawały dotychczas jako rzekoma osoba lub
  miejscowość. Prawdziwe nazwiska w tym samym miejscu („Rossi Mario”) są
  nadal rozpoznawane.

- Dwukolumnowe skany chronią teraz opisane identyfikatory i dane
  miejscowości także wtedy, gdy rozpoznawanie tekstu dostarcza najpierw
  wszystkie nagłówki pól, a potem wszystkie wartości. Przyporządkowanie
  podąża za widocznym wierszem pikseli i działa też przy stronach
  obróconych o 90 stopni. Ciasno rozdzielone części identyfikatora
  paszportowego lub umownego są zaciemniane wspólnie; opisane daty
  urodzenia, klucze ICD i PZN są również pokryte, następujące rzeczowniki
  pozostają nienaruszone. Krótkie nazwiska i nazwy użytkowników są
  chronione przy dokładnych polach; adresy e-mail rozłożone na kilka słów
  OCR tylko przy ciasnym sąsiedztwie i pełnej gramatyce e-mail.
  Przywiązana do pola korekta znaków dających się pomylić oraz lokalne
  doczytanie jeszcze pustego pola osobowego zamykają uszkodzone i obrócone
  skany, bez rozszerzania pól rzeczowych czy już obsadzonych wartości.
  Marginesy bezpieczeństwa podążają za wielkością słowa, a profil cechowy
  zabiera bezpośrednio sąsiadujące jednostki dawkowania i interwały
  płatności. Lekko krzywo wciągnięte formularze są geometrycznie
  rzutowane z powrotem z kilku zgodnych kierunkowo wierszy OCR; szum
  zaokrąglenia lub sprzeczni świadkowie nie wystarczają. Krótkie
  przedrostki literowe pozostają przed identyfikatorem z łącznikiem, a
  pełne opisane znalezisko adresu zastępuje tylko swoje jednorodne
  częściowe znalezisko ulicy. Błędnie odczytany nagłówek pola roli spada
  wyłącznie w kolumnie formularza obsadzonej co najmniej trzema znanymi
  nagłówkami; nazwy czatu pozostają chronione. Ciasne przycięcie
  marginesu i lokalna prześwietlenie z ukośnym odblaskiem świetlnym
  uzupełniają macierz obrazów. Znaleziska osób, miejscowości i firm
  sięgające przez kilka wierszy formularza są w wielokrotnie obsadzonej
  kolumnie pola ograniczane do danej wartości. Techniczna wartość pozycji
  spada tylko z nagłówkiem pozycji i pasującą formą identyfikatora;
  prawdziwe nazwiska pozostają chronione. Także wartości e-mail przerwane
  przez odblask świetlny są usuwane za wyraźnym nagłówkiem pola e-mail z
  ciasnym, ograniczonym sąsiedztwem marginesem obrazu. Dwie pary
  pole-wartość tego samego widocznego wiersza są teraz oceniane
  niezależnie; wartości na głębszej linii bazowej są łączone tylko po
  trzech zgodnych świadkach geometrycznych. Dzięki temu numery
  identyfikacyjne, daty urodzenia i adresy pozostają w pełni chronione
  także w gęstych układach formularzy. Ulica, kod pocztowy i miejscowość
  są łączone wyłącznie w obrębie tego samego pola adresu i z pasującą
  gramatyką pocztową. Ciasno zakreślone pola rzeczowe dla środków
  pomocniczych/roboczych i statusu zębów nie tworzą już fałszywych
  alarmów miejscowości czy spisu; prawdziwe nazwiska i podobnie nazwane
  pola pozostają chronione. Niemieckie laboratorium dokumentów obejmuje
  teraz 440 skanów i osiąga 2981/2981 w profilu podstawowym oraz
  3080/3080 w profilu cechowym. Wszystkie jedenaście mutacji obrazu i
  wszystkie 40 rodzin dokumentów leżą na 100 procentach, wciąż bez
  zmierzonego fałszywego alarmu, naruszenia zachowania czy przerwania.

- Warstwy tekstu PDF z utraconymi separatorami komórek ograniczają teraz
  znaleziska organizacji, adresów i miejscowości na podstawie
  powtarzającej się struktury pole-wartość. Nagłówki pól przed wartościami
  firmowymi i techniczne strzałki jak `=>` lub `->` nie należą już do
  trafienia. Dodatkowy widok dla miękkich złamań wiersza nie może już
  rozciągać znalezisk formy prawnej i miejscowości na kilka wierszy
  tabeli; już pełny adres kończy się przed następnym nagłówkiem pola wraz
  z wartością. Końcowy przebieg przez wszystkie 1600 dokumentów TXT,
  HTML, PDF i DOCX usuwa 10840/10840 wartości docelowych przy zero
  fałszywych alarmów, zero naruszeń zachowania i zero przerwań.

## 0.10.44-beta.1 – 1 września 2026

- Budowanie pakietów tworzy osobne pliki wyjściowe dla Windows x64 i ARM64,
  macOS na Apple Silicon i Intel oraz Linux x64 i ARM64. Nazwy pakietów,
  wybór aktualizacji i wydania rozróżniają architekturę; publikacja
  pozostaje zablokowana, dopóki brakuje jednego z sześciu celów lub jego
  dowodu zależności. Linux ARM64 wymaga ze względu na Qt co najmniej glibc
  2.39. W pełni odebrane na prawdziwym sprzęcie są na razie tylko
  Windows x64 i macOS na Apple Silicon; pozostałe pakiety architektur są
  wyraźnie oznaczone jako wersje wstępne do prób, nie do użytku
  produkcyjnego.

- Przy wielu plikach rozpoznawanie działa teraz dalej, podczas gdy podgląd
  czeka na przejrzenie. Do trzech przygotowanych podglądów jest pokazywanych
  po kolei; jednocześnie nadal liczy tylko jeden dokument,
  a plik wynikowy powstaje dopiero po jego zatwierdzeniu. Trwały wyjątek
  wybrany w podglądzie obowiązuje też dla już przygotowanych, kolejnych
  dokumentów.

- Certyfikaty redakcji można teraz w każdej chwili sprawdzić bezpośrednio
  w menu Plik względem zaczernionego dokumentu. Maskuro rozróżnia przy tym
  pasujący podpisany plik, pasujący, ale niepodpisany dowód, nieważny
  podpis i dokument nienależący do certyfikatu. Licencja
  ani pierwotne konto systemu operacyjnego nie są wymagane do kontroli.
  Dla automatycznych punktów kontrolnych ten sam sposób porównania jest
  dostępny przez `--zertifikat-pruefen`; kody zwrotne rozróżniają zgodność,
  błąd obsługi i nieważny dowód.
  Kontrola porównuje dodatkowo osadzony identyfikator Maskuro
  z certyfikatem; dowolnie wpisany obcy identyfikator zostaje przez to
  wykryty również przy niepodpisanym dowodzie.
  Przy ważnym podpisie wynik kontroli pokazuje ponadto aktywowanego przez
  administrację redaktora wraz z kontem systemu operacyjnego, technicznym
  identyfikatorem konta i platformą. Niepotwierdzone dane z niepodpisanych
  lub nieważnych dowodów nie są wyświetlane.

- Nowe niemieckie laboratorium dokumentów tworzy 160 w pełni syntetycznych
  dokumentów TXT, HTML, PDF i DOCX z dziesięciu obszarów i czterech
  wariantów struktury. Manifest rozróżnia teraz wyraźnie między
  danymi, które muszą zniknąć, a tekstami fachowymi
  oraz identyfikatorami rzeczowymi, które muszą zostać zachowane; rodzina
  dokumentu, mutacja i publiczne źródło struktury są udokumentowane
  w sposób możliwy do prześledzenia.

- Niemieckie laboratorium dokumentów zostało rozszerzone do 280 plików, siedmiu
  form struktury, 1540 wartości docelowych i 1036 kotwic zachowania. Nowo
  sprawdzane są numerowane formularze, oklamrowane pola PDF/maski i techniczne
  przypisania `=>`. Rozszerzony pełny stan osiąga w TXT, HTML, PDF i
  DOCX po 100 procent przy zerze fałszywych alarmów. Oklamrowane pola dat i
  numerów identyfikacyjnych, separatory strzałkowe i wyraźnie opisane grupy
  są teraz rozpoznawane strukturalnie.

- Drugie rozszerzenie laboratorium podnosi stan do 400 dokumentów, dziesięciu
  form struktury, 2200 wartości docelowych i 1480 kotwic zachowania. Wartości
  kluczowe w stylu JSON, listy YAML i wielkie pola formularzy osiągają razem
  z dotychczasowym stanem 100 procent przy zerze fałszywych alarmów. Cytowane
  daty urodzenia i numery identyfikacyjne oraz wyraźnie opisane role, takie
  jak osoby ubezpieczone, aplikujące, zobowiązane do złożenia i uprawnione
  do reprezentacji, są teraz rozpoznawane również w tych formach eksportu.

- Osobny tryb OCR niemieckiego laboratorium dokumentów tworzy dodatkowo
  200 czystych skanów obrazowych ze wszystkich 40 rodzin. Czyste,
  niskokontrastowe, o niskiej rozdzielczości, z artefaktami JPEG i obrócone
  o 90 stopni strony są mierzone ponownie za pomocą dokładnych ramek
  pikselowych, bez zmiany porównywalnego podstawowego stanu tekstowego
  1600 plików. Manifest oddziela włączalne cechy dat, kwot i medyczne
  od profilu podstawowego i zna udokumentowane odczyty OCR, nie licząc ich
  jako dodatkowe wartości docelowe. Pomiar jest rozbity według mutacji i
  rodziny dokumentu. Wąskie granice pól zapobiegają m.in. temu, że `Az` w
  nazwie miejscowości `Graz` zaczernia następującą datę jako sygnaturę akt;
  bieżąca macierz podstawowa działa z zerem fałszywych alarmów i zerem
  przerwań.

- Pięć kolejnych niemieckich rodzin dokumentów dla faktury/listu przewozowego,
  banku/kredytu, najmu/zarządu nieruchomości, szkoły/uczelni i
  logistyki/cła rozszerza laboratorium do 600 plików z 3520 wartościami
  docelowymi i 2360 kotwicami zachowania. Wąska ścieżka tabel PDF wykorzystuje
  wyraźny nagłówek `Feld Angabe` (Pole Wartość), gdy warstwa tekstu traci
  separatory komórek; nowy wybór `--familien` przyspiesza pomiary
  częściowe. 200 nowych plików
  osiąga 1320/1320 przy zerze fałszywych alarmów i zerze przerwań.

- Ubezpieczenie/szkoda, praca/wynagrodzenie, medycyna/laboratorium,
  pojazd/warsztat i technika/konserwacja rozszerzają niemieckie laboratorium
  dokumentów do 800 plików z 4960 wartościami docelowymi i 3200 kotwicami
  zachowania. Wąsko opisane identyfikatory polis, pacjentów, kontrolerów i
  pojazdów oraz nowe pola ról, adresów
  i organizacji są rozpoznawane. Nowa macierz częściowa i
  pełna macierz osiągają 100 procent przy zerze fałszywych alarmów i zerze
  przerwań w TXT, HTML, PDF i DOCX.

- Budowa/przetarg, energia/środowisko, stowarzyszenie/spółka,
  komunikacja/kalendarz i hotel/wydarzenie podnoszą niemieckie
  laboratorium dokumentów do 1200 plików z 7920 wartościami docelowymi i 4800
  kotwicami zachowania. Nowe pola ról, firm, adresów, rejestrów, zamówień,
  rezerwacji i kont użytkowników są rozpoznawane również we wszystkich
  formach eksportu. Numery liczników pozostają zachowane jako identyfikatory
  rzeczowe. Macierz częściowa i pełna osiągają 100 procent przy zerze
  fałszywych alarmów i zerze przerwań.

- Gastronomia/dostawa, apteka/recepta, pogrzeb/cmentarz,
  sport/członkostwo i nieruchomości/pośrednictwo rozszerzają niemieckie
  laboratorium dokumentów do 1400 plików z 9360 wartościami docelowymi i 5640
  kotwicami zachowania. Nowe role osób, pola adresowe i
  numery zleceń poszukiwania są rozpoznawane. Opisane nazwy firm z formą
  prawną pozostają w pełni chronione również po automatycznym złamaniu
  wiersza; klasy wiekowe i specjaliści nie są już fałszywie zastępowani.
  Macierz częściowa i pełna osiągają 100 procent przy zerze fałszywych
  alarmów i zerze przerwań.

- Leczenie stomatologiczne, szkoła jazdy, straż pożarna/interwencja,
  wspólnota energetyczna i podróż zorganizowana rozszerzają niemieckie
  laboratorium dokumentów do 1600 plików z 10 840 wartościami docelowymi i
  6440 kotwicami zachowania. Nowe role, pola adresowe
  oraz identyfikatory leczenia, kształcenia, interwencji, energii i
  umowy podróży są rozpoznawane strukturalnie. Nowa macierz częściowa
  200 plików osiąga 1480/1480; pełna macierz osiąga
  10 840/10 840. Obie pozostają przy zerze fałszywych alarmów i zerze
  przerwań.

- Pełny pomiar laboratorium dokumentów obniżył dzięki wąskim urzędowym
  formom rzeczowym i regułom struktury liczbę zbędnych zastąpień z
  68 do 0, liczbę wyraźnie mierzonych naruszeń zachowania z 23 do 0 i
  liczbę przerwań z 3 do 0.
  Odsetek wykryć wzrósł jednocześnie z 91,1 do 100,0 procent; TXT, HTML, PDF i
  DOCX osiągają po 100 procent. Ogólne
  nagłówki tabel, takie jak `Feld` (Pole), są hamowane tylko w udokumentowanej
  sekwencji `Feld`/`Angabe` (Pole/Wartość); identycznie brzmiące nazwisko
  pozostaje chronione. Sygnatury akt sądowych z literą końcową, pola ze
  znakiem równości,
  `Geburtsdatum des Kindes` (data urodzenia dziecka) i kilka opisanych
  pojedynczych nazwisk w tym samym
  wierszu są w pełni rozpoznawane. Tabele Word i pola nad wierszami
  wykorzystują
  swój nagłówek pola jako tymczasowy kontekst rozpoznawania; opisane
  adresy PDF pozostają w pełni chronione również przy złamaniu wiersza
  wynikającym ze zdania.

- Niemieckie pola cech osobowych, zawodów i medyczne działają teraz
  również z niemieckimi (Windows) znakami końca wiersza. Jednoliterowe
  oznaczenia płci, takie jak
  `Geschlecht`/`w` (Płeć/k), są chronione w formie z nagłówkiem nad wierszem.
  Rzeczowe pola
  `Artikel-PZN` (PZN artykułu) nie powodują natomiast ani wykrycia klucza
  leku, ani wykrycia osoby; prawdziwe wartości PZN, ICD i ATC
  pozostają rozpoznawane.

- Niemieckie pola formularzy i numerów są dokładniejsze: „DW." działa teraz
  również przed miękkim złamaniem wiersza, wyraźnie opisane nazwiska są
  usuwane nawet przy pisowni małymi literami, a czysto liczbowe sygnatury akt
  są przypisywane do właściwego rodzaju numeru identyfikacyjnego. I odwrotnie:
  przypadkowo zgodny z algorytmem Luhna numer faktury, dowodu lub artykułu nie
  jest już uznawany za kartę kredytową. Syntetyczne próbki wyjściowe HTML i
  PDF potwierdzają usuwanie i zachowywanie w gotowym dokumencie.
  Numery identyfikacyjne i nazwy użytkowników są ponadto rozpoznawane, gdy
  ich opis stoi w bezpośrednio poprzedzającym wierszu tabeli lub
  formularza; rzeczowe numery dowodów pozostają widoczne również w tej
  formie.

- Hasła są teraz rozpoznawane również za samodzielnym nagłówkiem pola w
  poprzednim wierszu. Kończące znaki specjalne, takie jak `!` lub `#`,
  należą przy tym w pełni do chronionej wartości. Numery PIN produktów i
  artykułów nie są odwrotnie już maskowane jako PIN karty; wyraźne
  pola „PIN" i „Karten-PIN" (PIN karty) pozostają chronione.

- Wartości formularzy pisane małymi literami są teraz przy jednoznacznych
  niemieckich polach adresowych i `PLZ/Ort` (kod pocztowy/miejscowość)
  wyprowadzane jako adres lub kod pocztowy z miejscowością zamiast tylko
  jako ogólne miejsce. Podobnie pisane małymi literami wartości firmowe,
  takie jak „przykładowy serwis", pozostają w pełni chronione za polem
  firmy, bez ucinania ostatniego słowa jako rzekomego kolejnego nagłówka
  pola.

- Pomoc, FAQ, tekst o ochronie danych i strona internetowa wyjaśniają teraz
  wspólnie dowód pochodzenia: neutralny identyfikator Maskuro w dokumencie,
  opcjonalne przyporządkowanie do prawdziwego konta systemu operacyjnego
  tylko w lokalnym protokole kontroli, zmianę użytkownika w
  Windows/macOS/Linux oraz siłę wymowy SHA-256 i podpisu.

- Oparte na obrazie techniczne przedmiary robót są oczyszczane bardziej
  powściągliwie. Jednoznaczne słowa rzeczowe, takie jak „Abbruchhämmern"
  (kucie młotami wyburzeniowymi), „Deckungsrücklass" (zatrzymanie
  gwarancyjne), „Positionsnummern" (numery pozycji), „Einbauplatine"
  (płytka montażowa) lub „Terminsituation" (sytuacja terminowa) oraz formy
  OCR rozdzielone w środku słowa nie są już uznawane za osobę lub miejsce.
  Rzeczywista oferta urzędu gminy spadła dzięki temu ze 140 do 90
  jednoznacznych zastąpień, bez tworzenia nowych trafień; nazwiska takie
  jak Schneider, Lang, Bauer i Hahn pozostają wyraźnie chronione.

- Usunięto kolejne fałszywe alarmy z rzeczywistych ofert: „Digital signiert"
  (podpisano cyfrowo) nie zawiera już rzekomej osoby, BIC jest rozpoznawany
  również bez dwukropka za swoim opisem, `15000 Alternativ` nie jest już
  uznawane za kod pocztowy z miejscowością, a cytat UE „(VO (EG) 715/2007"
  nie tworzy już organizacji. Oferta fotowoltaiczna spadła dzięki temu z 26
  do 16 przypadków zastąpienia; prawdziwe nazwiska, miejsca i dane konta
  pozostały zachowane.

- W przeglądach pracowników skrót zastępcy „Stv." oraz samodzielnie
  odseparowany nagłówek obszaru „FACILITY" nie są już zastępowane jako
  nazwisko osoby. Rzeczywista 13-stronicowa kontrola porównawcza spadła z 878
  do 875 zastąpień; nazwiska, numery wewnętrzne i nazwa firmy pozostały
  chronione.

- Oczyszczone pliki PDF, OpenDocument i Office otrzymują neutralny
  identyfikator „MASKURO-…" we właściwościach dokumentu. Protokół kontroli
  i podpisany protokół kontroli zawierają ten sam identyfikator oraz
  wartości SHA-256 źródła i wyniku; certyfikat redakcji przejmuje
  identyfikator z gotowego pliku. Nazwa użytkownika jest nadal dodawana
  tylko wtedy, gdy administracja wyraźnie włączy istniejące pole
  użytkownika.

- Okno główne i ustawienia mają spokojniejszy układ: Zapisz, Kopiuj,
  Szczegóły, Wskaźniki i usuwanie profilu rozpoznawania pojawiają się
  dopiero, gdy dana czynność jest możliwa. Techniczne skróty językowe OCR i
  długie przykłady stoją w razie potrzeby w tekście wskazówki zamiast na
  stałe na obszarze roboczym. Strona rozpoznawania lepiej dostosowuje się
  do węższych okien, bez uciętych wyjaśnień czy poziomego paska
  przewijania; ostrzeżenie o czystym tekście na liście zastąpień pozostaje
  przy tym widoczne.

- Rozpoznawanie obejmuje kolejne niemieckie i międzynarodowe przypadki
  kontaktowe: numery telefonów są teraz sprawdzane dla wszystkich
  wybieralnych regionów krajowych, węgierskie i chorwackie role umowne
  wykrywają teraz w pełni również nazwiska zgodne z zawodem, a numerowane
  listy części zamiennych/materiałów nie wywołują już fałszywego alarmu
  osobowego z powodu „Mutter / Flach" (nakrętka/płaski). Pola osobowe z
  wyraźnie liczbową wartością rzeczową nie są przejmowane jako nazwisko;
  strefa odczytu maszynowego (MRZ) można ponadto włączać i wyłączać
  wspólnie przez grupę „Identyfikatory".

- Firmy bez formy prawnej są lepiej odróżniane od osób za wieloznacznymi
  polami pracodawcy: nazwy takie jak „Huber Handel", „Müller Logistik" czy
  „Kowalski Handel" są w pełni wykrywane jako firma, podczas gdy
  „Arbeitgeber: Bauer Anna" (Pracodawca: Bauer Anna) pozostaje nazwiskiem
  osoby. Automatyczny wybór kraju nadal uwzględnia przy dokumentach
  francuskich cały francuski obszar językowy łącznie z Luksemburgiem.

- Rozpoznane podpisy odręczne i tekst zawierający dane osobowe wewnątrz
  obrazu były dotychczas zawsze zakrywane czarnym prostokątem – nawet jeśli
  dla zaczernień ustawiono inny kolor lub wzór, taki jak „Tęcza". Te
  obszary obrazu przejmują teraz również wybraną prezentację zaczernienia;
  kryjąca powierzchnia jest nadal zapisywana bezpośrednio w pikselach
  obrazu.

- Rozpoznawanie języka angielskiego zostało zmierzone i celowo ulepszone na
  jedenastu ręcznie przetłumaczonych, prawdziwych dokumentach: status
  inwentarza, techniczne pola ofertowe i sklepu internetowego oraz role w
  katalogach pracowników pozostają widoczne, „CV" nie jest już odczytywane
  w zestawie szablonów jako forma prawna, cytowane czcionki pozostają
  zachowane, a nazwiska w pionowych nagłówkach życiorysów, wielostronicowych
  listach pracowników, za „Account manager" oraz nazwy firm zaczynające się
  od cyfr są w pełni rozpoznawane. Austriackie numery rejestru handlowego
  działają teraz również za angielskim opisem; skrócona forma „Customer:",
  numery rejestracyjne EAR i numery pracodawcy niosą swoją wartość. Łańcuchy
  wymiarów, typy kabli, odniesienia do prawa UE, daty ważności ofert,
  miejsca wykonania, siedziby sądów, sądy rejestrowe, skrót podatkowy
  „NoVA", numery techniczne na etykietach opon oraz odniesienia normatywne,
  takie jak „OVE R6-2" i „AStV", nie powodują już fałszywego alarmu. Ważny
  opisany IBAN kończy się czysto przed polem rejestracji lub nagłówkiem
  kolejnego wiersza; adresy z dodatkiem strefy przemysłowej są w pełni
  rozpoznawane również z tekstowych strumieni PDF ze znakami końca wiersza
  systemu Windows. Angielskie wstępy firmowe i strukturalne nazwy kas
  oszczędnościowych są w pełni odgraniczane. Kraj dokumentu źródłowego
  pozostaje zachowany w wersjach językowych dla kodów pocztowych i
  identyfikatorów specyficznych dla kraju.

- W wierszach odbiorcy i nagłówka wiadomości model językowy mógł łączyć
  pierwsze dwa nazwiska z listy oddzielonej przecinkami w jedno trafienie
  („Bcc: Huber, Mayer"). Oba nazwiska są teraz rozpoznawane, zastępowane i
  ujmowane w raporcie osobno – tak samo za „Sent:", „Reply:" i „Fwd:".

- Strefa odczytu maszynowego paszportu lub dowodu osobistego (MRZ) brakowała
  w sterowaniu grupowym „Co jest wyszukiwane". Należy teraz do „Identyfikatory"
  i można ją włączać i wyłączać razem z tą grupą.

- Kto dla tekstów zastępczych wybierze szablon „Tęcza", dostanie teraz
  również zaczernione miejsca w tym samym wyglądzie; dotychczas pozostawały
  one zaskakująco klasycznie czarne. Powierzchnie zaczernienia można potem
  nadal niezależnie przełączyć na inny szablon.

- Panel boczny stron edytora poprawek mógł pozostać pusty po przywróceniu
  zapisanego układu okna, dopóki jego szerokość nie została zmieniona
  ręcznie. Miniatury są teraz porządkowane na nowo po widocznej budowie
  okna i stoją od razu wyśrodkowane w panelu.

- Kolorowe znaczniki kontrolne wokół tekstów zastępczych w PDF były w
  zależności od koloru kategorii i sygnalizacji ledwo widoczne. Jasna
  podkontura oddziela teraz ramkę kontrolną niezawodnie od kolorowego
  symbolu zastępczego i od tła strony.

- Kto w edytorze poprawek zaczernia wiersz dokumentu ustawionego z wąskim
  odstępem wierszy (typowe dla ofert i przedmiarów robót), otrzymywał
  pasek, który wchodził w górne wydłużenia wiersza poniżej – był potem
  tylko w połowie czytelny. Pasek kończy się teraz na faktycznie
  narysowanym piśmie sąsiedniego wiersza; sam zaczerniony wiersz wraz z
  jego dolnymi wydłużeniami pozostaje przy tym w pełni zakryty.

- Dokument ćwiczeniowy („Pomoc → Otwórz dokument ćwiczeniowy", również w
  oprowadzeniu) prezentuje teraz każdy rodzaj rozpoznawania: do zmyślonego
  listu dochodzą zdjęcie z rozpoznawalną twarzą, odręczny podpis, zawód i
  dział, diagnoza i lek – obok nazwy firmy, kwoty i daty, które już tam
  były. Co ustawienie domyślne celowo zostawia bez zmian, wyjaśnia sam
  arkusz, wraz z przełącznikiem, który to usuwa; twarz na zdjęciu jest
  fabrycznie pikselowana.

- Kwoty pieniężne w zwykłej niemieckiej pisowni z symbolem za liczbą
  („1.240,00 €") nigdy nie były znajdowane przez przełącznik „Usuń również
  kwoty pieniężne" – „1.240,00 EUR" i „€ 1.240,00" zawsze tak. Teraz
  rozpoznawane są wszystkie trzy sposoby zapisu.

- Wyszukiwanie podpisów działa teraz również na samodzielnych plikach
  obrazów: kto oczyszcza skan jako JPG lub PNG, dostanie zaczernione w nim
  odręczne podpisy – to samo rozpoznawanie, ten sam komunikat w raporcie
  co przy PDF. Obrazy osadzone w plikach Office nadal nie są przeszukiwane,
  ponieważ rozpoznawanie działa tam pomiarowo niewiarygodnie; pole wyboru
  nazywa się teraz „PDF i pliki obrazów: zaczernij odręczne podpisy".

- Pasek zaczernienia mógł przy wąskim odstępie wierszy widocznie wchodzić w
  górne wydłużenia wiersza poniżej i czynić go w połowie nieczytelnym –
  wysokość paska pochodziła z metryk czcionki, a nie z tego, co
  rzeczywiście jest na papierze. Pasek kończy się teraz na faktycznie
  narysowanym tuszu sąsiedniego wiersza, zarówno w edytorze poprawek, jak i
  w automatycznym oczyszczaniu. Własny wiersz wraz z dolnymi wydłużeniami
  pozostaje przy tym zawsze całkowicie zakryty; jeśli wiersze rzeczywiście
  się nakładają, pasek raczej pozostaje na sąsiednim wierszu, niż coś
  odsłania.

- W katalogu pracowników z rolą pod nazwiskiem żeńskie oznaczenie
  kierownicze („Anna Berger" z „Montageleiterin" (kierowniczka montażu)
  pod spodem) zostało wciągnięte do zastąpienia nazwiska – forma męska
  obok pozostała poprawnie na miejscu. Żeńskie formy „…leiterin"
  (Montage-, Team-, Projekt-, Bau-, Abteilungs-, Betriebs-, Gruppen-,
  Amtsleiterin) są teraz traktowane jak ich męskie odpowiedniki jako
  oznaczenie funkcji; kierownictwo filii, personalne i sprzedaży są nowe w
  obu formach.

- Włączane rozpoznawanie zawodów nie znajdowało żeńskich ról kierowniczych,
  takich jak „Projektleiterin", „Teamleiterin" czy „Abteilungsleiterin", ich
  męskie formy jednak tak. Obie formy liczą się teraz tak samo.

- W oknie podglądu na Macu wielokrotne oznaczenie sklejało się bezpośrednio
  z pojęciem („Anna Musterfrau2ק zamiast „Anna Musterfrau 2ק). Odstęp jest
  z powrotem.

- Lupa porównawcza ma nowy przycisk obok suwaka powiększenia: jednym
  naciśnięciem układa ją na pełną szerokość nad wynikiem – po połowie
  wysokości, a oryginał w tej samej skali co dokument (powiększenie lupy
  skacze przy tym na 100%). Drugie naciśnięcie dokuje ją z powrotem małą
  w lewej kolumnie i przywraca poprzednie powiększenie lupy. Kółko obok
  ustawia teraz tylko powiększenie od nowa – jego tekst wskazówki
  dotychczas błędnie twierdził, że doku­je też z powrotem okno.

- Na pasku narzędzi edytora poprawek znów widać, że wybrane narzędzie jest
  wybrane: przycisk aktywnego narzędzia ma wypełnioną powierzchnię z
  niebieską obwódką – tak samo każdy inny włączony przycisk przełącznikowy
  paska (np. lupa porównawcza lub tryb nauki). Oznaczenie zostało utracone
  wraz z własną stylizacją przycisków z 29 sierpnia.

- Numery pozycji przedmiaru robót („2.3.3.3, 2.3.3.4, 2.3.3.5" jeden pod
  drugim) były uznawane za adresy IP i usuwane z wyniku; trzystopniowe
  numery z końcowym elementem podobnym do roku („2.3.19, 2.3.20") padały
  jako daty kalendarzowe. Rosnąca sekwencja numerów na początku wiersza
  jest teraz uznawana za to, czym jest – listę pozycji; prawdziwe adresy
  (tabele sieciowe z technicznym otoczeniem słownym, liczby powyżej 99) i
  prawdziwe daty pozostają nadal rozpoznawane.

- Nazwiska takie jak „Müller", „Fischer", „Bauer", „Koch", „Wagner",
  „Schneider", „Weber", „Jäger", „Schmied", „Becker", „Schuster", „Schäfer"
  czy „Meister" pozostawały w listach postaci „Nazwisko, Imię" (np.
  „Teilnehmer: Müller, Peter; Nowak, Anna") w czystym tekście, ponieważ są
  jednocześnie powszechnymi nazwami zawodów. Są teraz niezawodnie
  rozpoznawane.

- Podczas zaczerniania pliku PDF pasek mógł w wąskich komórkach tabeli
  zabrać całą komórkę: z trafienia „D-LINK" w przedmiarze robót powstało
  usunięcie całego opisu produktu obok, mimo że podgląd wymieniał tylko
  trafienie. Pasek nadal zakrywa całe wiersze bloku adresowego i opisy
  pól, ale połyka co najwyżej tyle niezwiązanego tekstu, ile zakrywa
  wartego ochrony – opis obok trafienia pozostaje teraz na miejscu.

- Po „Przywróć widok" w edytorze poprawek panel stron pozostawał pusty –
  miniatury stron były widoczne dopiero po zamknięciu i ponownym otwarciu
  okna. Teraz stoją tam też bezpośrednio po zresetowaniu, wyśrodkowane jak
  wcześniej.

- Edytor poprawek ma czwarte narzędzie: **Usuń** wyjmuje tekst pod ramką
  bez zastępowania – bez paska (zaczernianie) i bez symbolu zastępczego
  (zastępowanie); luka pozostaje widocznie pusta. Działa dokładnie na
  słowach, jeśli pod spodem znajduje się obraz, jego tło jest czyszczone na
  biało, a „Przywróć oryginał" cofa również usunięcie bez zastępowania.
  Własny symbol na pasku i odznaka celownika (krzyżyk), własny skrót we
  wszystkich 18 językach (niemiecki F jak entFernen).

- Na pasku wyszukiwania PDF „Folder …" stoi teraz po prawej stronie opcji
  wyszukiwania. Odkąd oprócz zaczerniania istnieje też zastępowanie
  trafień, pięć przycisków nie mieściło się już obok siebie przy zwykłej
  szerokości okna – pierwszy był ściśnięty, a jego tekst ucięty.

- „Zresetuj wszystkie ustawienia" resetuje teraz również pole wyboru
  „Zastąp czerwony/zielony innymi kolorami" i odnotowuje je jak każde inne
  jako „zmienione", gdy odbiega od stanu fabrycznego.

- Teksty zastępcze w PDF działają teraz bardziej równomiernie: tam, gdzie
  pełny symbol zastępczy musiałby być wyraźnie mniejszy niż jego wiersz
  (np. „[BEG16]" wciśnięte w krótkie słowo, takie jak „Das"), pojawia się
  zamiast tego skrócona forma w rozmiarze wiersza („[B16]") – dobrze
  czytelna zamiast maleńka, a numer do przywracania niesie obie pisownie.
  Maleńki symbol zastępczy pojawia się tylko wtedy, gdy nawet najkrótsza
  forma nie znajduje miejsca – to pozostaje lepsze niż pasek bez żadnej
  informacji.

- Wielokolorowo ustawiony tekst zastępczy (gradient lub tęcza) w PDF
  pozostawał nienaruszony tylko do następnej ingerencji: każde kolejne
  zastąpienie lub zaczernienie na tej samej stronie mogło już ustawione
  symbole zastępcze spleść w nieczytelny, ściśnięty stos liter – kto w
  edytorze zastępował słowo po słowie, widział zamiast „[BEG17]" tylko
  nadrukowane na sobie znaki. Raz ustawione symbole zastępcze pozostają
  teraz takie, jakimi zostały ustawione.

- Przełącznik trwałych wyjątków w podglądzie nazywa się teraz „Nigdy nie
  usuwaj" – jak lista, do której wpisuje; dotychczas stało tam „nigdy
  więcej". Wiersz trafienia obok jest bardziej uporządkowany: symbol
  informacji „ⓘ" jest większy i łatwiejszy do trafienia, a pole wyboru,
  znacznik zastąpienia i przycisk mają wspólną wysokość. Zdanie wokół
  trafienia wykorzystuje teraz naprawdę zapowiedzianą szerokość –
  dotychczasowe podanie szerokości było przez wyświetlanie po cichu
  odrzucane, a fragment łamał się dalej jako wąski pasek.

- W edytorze wskaźnik myszy pokazuje teraz, które narzędzie działa:
  celownik do celowania, obok mały znak – pasek do zaczerniania, strzałki
  wymiany do zastępowania, łuk cofania do przywracania, siatka pikseli do
  pikselowania. Dotychczasowe symbole ręki odpadły; ręka oznacza wszędzie
  indziej „chwyć i przesuń". Ma teraz odpowiednie zadanie: nad czerwono
  wyróżnionym słowem lub paskiem wskaźnik zamienia się we wskazującą rękę
  – tam wystarczy jedno kliknięcie.

- „Maksymalne rozpoznawanie (AI)" nie oferuje już pobieranego, lokalnego
  modelu językowego – ten poziom liczy teraz wyłącznie za pośrednictwem
  własnej AI skonfigurowanej pod „Podłącz własną AI". Kto już wcześniej
  podłączył własny serwer, nie zauważy różnicy.

- Przewodnik po podglądzie wyjaśnia teraz również symbol informacji „ⓘ",
  który pokazuje zdanie wokół trafienia. I samo to zdanie jest lepiej
  czytelne: o stopień większa czcionka, więcej odstępu między wierszami,
  stała szerokość zamiast wąskiego, ściśniętego łamania.
- Także „Sprawdź plik", „Reguły rozpoznawania i własne pojęcia", „Oczyść
  tekst" i „Oczyść obraz" mają teraz własne oprowadzenie – przez nowy
  przycisk „Oprowadzenie po oknie", ponieważ te cztery okna nie mają
  własnego paska menu.
- Nazwiska pod dziewięcioma ukraińskimi opisami ról umownych pozostawały
  częściowo nierozpoznane przy homograficznym nazwisku, gdy opis stał
  samodzielnie w swoim wierszu: „Покупець"/„Продавець" (Kupujący/Sprzedający),
  „Поручитель"/„Боржник" (Poręczyciel/Główny dłużnik), „Свідок" (Świadek),
  „Орендодавець"/„Орендар" (Wynajmujący/Najemca) i
  „Спадкодавець"/„Спадкоємець" (Spadkodawca/Spadkobierca). Nazwiska są teraz
  w pełni rozpoznawane.

- Komentarz nazwanego zakresu w skoroszycie Excel (Menedżer nazw, pole
  „Komentarz") niósł wpisane w nim nazwisko bez zmian dalej. Jest teraz
  oczyszczany tak samo jak pozostała zawartość skoroszytu.

- Nazwiska pod siedmioma węgierskimi opisami ról umownych pozostawały przy
  homograficznym nazwisku całkowicie niewykryte: „Bérbeadó"/„Bérlő"
  (Wynajmujący/Najemca), „Vevő"/„Eladó" (Kupujący/Sprzedający),
  „Kezes"/„Főadós" (Poręczyciel/Główny dłużnik) i „Tanú" (Świadek).
  Nazwiska są teraz w pełni rozpoznawane.

- Nazwiska pod czeskim opisem kupującego „Kupující" pozostawały przy
  homograficznym nazwisku całkowicie niewykryte. Nazwisko jest teraz w
  pełni rozpoznawane.

- Nazwiska pod rosyjskim opisem opiekuna „Опекун" pozostawały przy
  homograficznym nazwisku całkowicie niewykryte. Nazwisko jest teraz w
  pełni rozpoznawane.

- Nazwiska pod sześcioma kolejnymi chorwackimi opisami pozostawały
  niewykryte: „Jamac" (Poręczyciel), „Glavni dužnik"/„Dužnik" (Główny
  dłużnik/Dłużnik), „Ostavitelj" (Spadkodawca), „Nasljednik" (Spadkobierca)
  i „Vjerovnik" (Wierzyciel). Nazwiska są teraz w pełni rozpoznawane.

- Zapisana strona HTML z osadzoną podstroną w atrybucie `src` elementu
  `<embed>` (zamiast `data` przy `<object>`) niosła dane osobowe w niej
  bez zmian dalej. Są teraz oczyszczane tak samo jak przy `<object>`.

- Nazwiska pod pięcioma duńskimi opisami ról umownych pozostawały przy
  homograficznym nazwisku częściowo nierozpoznane, gdy opis stał z
  dwukropkiem przed nazwiskiem: „Arvelader"/„Arving" (Spadkodawca/Spadkobierca),
  „Befuldmægtiget"/„Fuldmagtsgiver" (Pełnomocnik/Mocodawca) i „Værge"
  (Opiekun). Nazwiska są teraz w pełni rozpoznawane; odpowiednie
  norweskie opisy zostały dla zabezpieczenia również dodane.

- Symbole zastępcze w plikach Word i PowerPoint mają teraz ten sam kolor,
  co w wybranym wyglądzie (jednokolorowy, gradient, tęcza lub według
  kategorii) – dotychczas pozostawały tam w zwykłym kolorze tekstu, nawet
  jeśli wyniki PDF były już od dawna kolorowe.

- „Kopiuj jako tekst" i „Kopiuj jako Markdown" umieszczają czysty tekst
  wyniku bezpośrednio w schowku – do wklejenia w czat, mail lub inny
  program, bez konieczności wcześniejszego otwierania pliku.

- Nazwiska pod pięcioma kolejnymi słoweńskimi opisami pozostawały
  niewykryte: „Toženec" (Pozwany), „Tožnik" (Powód), „Zastavitelj"
  (Zastawca), „Zastavni upnik" (Wierzyciel zastawny) i „Darovalec"
  (Darczyńca). Nazwiska są teraz w pełni rozpoznawane.

- Nazwisko autora śledzonej zmiany komórki tabeli (wstawiona, usunięta lub
  scalona komórka w Word) pozostawało w pliku, nawet jeśli to samo
  nazwisko jako autor komentarza było już od dawna usunięte. Jest teraz
  również usuwane.

- Nazwiska pod dziewięcioma kolejnymi słoweńskimi opisami pozostawały
  niewykryte: „Najemodajalec"/„Najemnik" (Wynajmujący/Najemca),
  „Zapustnik"/„Dedič" (Spadkodawca/Spadkobierca), „Upnik"/„Dolžnik"
  (Wierzyciel/Dłużnik), „Glavni dolžnik" (Główny dłużnik) i „Skrbnik"
  (Opiekun/Kurator). Nazwiska są teraz w pełni rozpoznawane.

- Nazwiska pod pięcioma słoweńskimi opisami pozostawały niewykryte:
  „Izvedenec" (Biegły), „Kupec" (Kupujący), „Prodajalec" (Sprzedający),
  „Naročnik" (Zamawiający) i „Izvajalec" (Wykonawca). Nazwiska są teraz w
  pełni rozpoznawane.

- Nazwiska pod pięcioma kolejnymi litewskimi opisami pozostawały
  niewykryte: „Užsakovas" (Zamawiający), „Vykdytojas" (Wykonawca),
  „Vežėjas" (Przewoźnik), „Siuntėjas" (Nadawca) i „Arbitras" (Arbiter).
  Nazwiska są teraz w pełni rozpoznawane.

- Nazwiska pod sześcioma kolejnymi litewskimi opisami pozostawały
  niewykryte: „Įgaliotinis" (Pełnomocnik), „Įgaliotojas" (Mocodawca),
  „Naudos gavėjas" (Uposażony, ubezpieczenie), „Trečiasis asmuo" (Interwenient
  uboczny/strona trzecia w procesie cywilnym), „Ankstesnis nuomininkas"
  (Poprzedni najemca) i „Naujasis nuomininkas" (Nowy najemca). Nazwiska są
  teraz w pełni rozpoznawane.

- Zakładka w dokumentach ODT (`text:bookmark`) niesie swoją nazwę swobodnie
  nadaną, często nazwaną według miejsca, do którego wskazuje (np.
  „Herr_Mueller_Unterschrift" – Pan_Mueller_Podpis) – niewidoczna dla
  czytelnika, ale zapisana dosłownie w pliku. Nazwa jest teraz również
  oczyszczana.

- Nazwiska pod ośmioma kolejnymi litewskimi opisami pozostawały
  niewykryte: „Pareiškėjas" (Wnioskodawca), „Suinteresuotas asmuo" (Uczestnik
  postępowania nieprocesowego), „Ekspertas" (Biegły/rzeczoznawca),
  „Bankroto administratorius" (Syndyk masy upadłości), „Valdybos narys"
  (Członek rady nadzorczej), „Direktorius" (Dyrektor zarządzający),
  „Palikėjas" (Spadkodawca) i „Įpėdinis" (Spadkobierca). Nazwiska są teraz
  w pełni rozpoznawane.

- Nazwiska pod siedmioma kolejnymi litewskimi opisami pozostawały
  niewykryte: „Liudytojas" (Świadek), „Vertėjas" (Tłumacz), „Notaras"
  (Notariusz), „Dovanotojas" (Darczyńca), „Apdovanotasis" (Obdarowany),
  „Pirkėjas" (Kupujący) i „Pardavėjas" (Sprzedający). Nazwiska są teraz w
  pełni rozpoznawane.

- Nazwiska pod sześcioma kolejnymi litewskimi opisami pozostawały
  niewykryte: „Globėjas" (Opiekun/Kurator), „Palikimo administratorius"
  (Zarządca spadku), „Laiduotojas" (Poręczyciel), „Pagrindinis skolininkas"
  (Główny dłużnik), „Nuomotojas" (Wynajmujący) i „Nuomininkas" (Najemca).
  Nazwiska są teraz w pełni rozpoznawane.

- Nazwisko pod litewskim opisem „Ieškovas"/„Atsakovas" (Powód/Pozwany jako
  strona procesowa) pozostawało niewykryte, niezależnie od tego, czy
  nazwisko było jednocześnie powszechnym słowem (np. „Vilkas" = Wilk) czy
  nie. Nazwisko jest teraz w pełni rozpoznawane.

- Wpis rejestru osób w dokumentach ODT (zakładka do skorowidza) niósł
  nazwisko po raz drugi we własnym kluczu sortowania – niewidoczne w tekście
  ciągłym, ale zapisane dosłownie w później tworzonym skorowidzu. Klucz
  jest teraz również oczyszczany.

- Nazwa slajdu i nazwa sekcji prezentacji PowerPoint (widoczne w obszarze
  wyboru lub w sortowaniu slajdów) pozostawały nieoczyszczone, ponieważ obie
  są przypisane jako atrybut do elementu, który nie jest tekstem slajdu.
  Obie są teraz rozpoznawane.

- Litewskie podwójne nazwisko z łącznikiem, takie jak „Petraitis-Kazlauskas",
  traciło swoją drugą połowę, gdy tylko jakikolwiek tekst ciągły stał przed
  nim (tylko na początku tekstu pozostawało pełne): nazwisko jest teraz
  rozpoznawane w całości również w tym przypadku.

- Nazwisko pod opisem „Cesionar" (chorwacki, cesjonariusz przy cesji
  wierzytelności) powodowało fałszywy alarm, ponieważ sam opis pola był
  błędnie odczytywany jako osoba. Nazwisko pod rosyjskim opisem
  „Цессионарий" (również cesjonariusz) pozostawało natomiast całkowicie
  niewykryte. Oba przypadki są teraz naprawione.

- Nazwisko pod opisem „Zedent"/„Zessionar" (niemiecki, cesja wierzytelności)
  pozostawało bez ochrony całkowicie niewykryte, gdy nazwisko było
  jednocześnie powszechnym słowem (np. „Bauer"). Nazwisko jest teraz w
  pełni rozpoznawane.

- Nazwisko pod opisem „Darczyńca"/„Obdarowany" (polski, darczyńca/obdarowany
  w umowie darowizny) pozostawało niewykryte, gdy nazwisko było
  jednocześnie powszechnym słowem (np. „Wilk" = Wolf). Podobnie rumuński
  opis „Donatar" (obdarowany) zawisał przy zwykłym nazwisku nawet jako
  rzekomy element nazwy. Oba przypadki są teraz naprawione.

- Nazwisko pod opisem „Wierzyciel"/„Dłużnik" (polski, wierzyciel/dłużnik
  egzekucyjny lub ogólny wierzyciel/dłużnik) pozostawało niewykryte, gdy
  nazwisko było jednocześnie powszechnym słowem (np. „Wilk" = Wolf).
  Nazwisko jest teraz w pełni rozpoznawane.

- Nazwisko pod opisem „Poręczyciel"/„Dłużnik główny" (polski, poręczyciel/
  główny dłużnik w umowach poręczenia) pozostawało niewykryte, gdy nazwisko
  było jednocześnie powszechnym słowem (np. „Wilk" = Wolf). Nazwisko jest
  teraz w pełni rozpoznawane.

- Nazwisko pod opisem „Ubezpieczony"/„Ubezpieczający" (polski, ubezpieczony/
  ubezpieczający w polisach ubezpieczeniowych) pozostawało częściowo lub
  całkowicie niewykryte, gdy nazwisko było jednocześnie powszechnym słowem
  (np. „Wilk" = Wolf). Podobnie nazwisko pod „Osiguranik"/„Osiguravatelj"
  (chorwacki, te same role), tam znikało nawet wraz z imieniem
  (np. „Golub" = Gołąb). Oba nazwiska są teraz w pełni rozpoznawane.

- Nazwisko pod opisem „Pełnomocnik"/„Mocodawca" (polski, pełnomocnik/
  mocodawca w pełnomocnictwach) pozostawało niewykryte, gdy nazwisko było
  jednocześnie powszechnym słowem (np. „Wilk" = Wolf). Podobnie nazwisko
  pod „Opunomoćenik"/„Opunomoćitelj" (chorwacki, te same role), tam
  znikało nawet całkowicie wraz z imieniem. Oba nazwiska są teraz w pełni
  rozpoznawane.

- Nazwisko pod opisem „Pozwany" (polski, pozwany jako strona procesowa)
  pozostawało niewykryte, gdy nazwisko było jednocześnie powszechnym
  słowem (np. „Wilk" = Wolf). Nazwisko jest teraz w pełni rozpoznawane.

- Nazwisko pod opisem „Najmoprimac"/„Najmodavac" (chorwacki, najemca/
  wynajmujący w umowach najmu) pozostawało niewykryte, gdy nazwisko było
  jednocześnie powszechnym słowem (np. „Kovač" = Kowal). Nazwisko jest
  teraz w pełni rozpoznawane.

- Nazwisko pod opisem „Pracodawca"/„Pracownik" (polski, pracodawca/
  pracownik jako strona umowy w umowach o pracę) pozostawało częściowo
  niewykryte, gdy nazwisko było jednocześnie powszechnym słowem (np.
  „Krawiec" = Schneider). Nazwisko jest teraz w pełni rozpoznawane.

- Węgry miały w katalogu krajów tylko identyfikatory osobowe i numer VAT:
  numer rejestru handlowego (Cégjegyzékszám) jest teraz rozpoznawany,
  jeśli słowo pola „Cégjegyzékszám" lub skrót „Cg." stoi bezpośrednio
  przed nim – sam numer nie ma cyfry kontrolnej.

- Estonia miała w katalogu krajów tylko Isikukood: Käibemaksukohustuslase
  number (numer VAT na każdej estońskiej fakturze) jest teraz rozpoznawany
  z cyfrą kontrolną.

- Łotwa miała w katalogu krajów tylko Personas kods: PVN reģistrācijas
  numurs osób prawnych (identyfikator firmy na każdej łotewskiej fakturze)
  jest teraz rozpoznawany z cyfrą kontrolną.

- E-mail z zaszyfrowaną treścią (koperta S/MIME lub PGP/MIME,
  `multipart/encrypted`) był wydawany bez żadnego ostrzeżenia jako
  rzekomo w pełni sprawdzony, chociaż jego właściwa treść była zaszyfrowana
  i tym samym niesprawdzona. Takie maile wskazują teraz na to jak
  niesprawdzony załącznik.

- Malta brakowała w katalogu krajów: maltański numer VAT jest teraz
  rozpoznawany.

- Luksemburg brakował w katalogu krajów: luksemburski numer VAT (n° TVA)
  jest teraz rozpoznawany.

- Bułgarskie „Изчакайте" ("Proszę czekać!") na początku zdania było
  zgłaszane jako nazwa miejsca – ta sama granica modelu, co wcześniej przy
  węgierskich, polskich, czeskich i innych formach wezwania bez własnego
  modelu językowego. Ten fałszywy alarm teraz nie występuje.

- Nazwisko pod opisem „Zleceniodawca", „Zleceniobiorca" (polski),
  „Prestator" (rumuński), „Naručitelj" lub „Izvođač" (chorwacki)
  pozostawało częściowo lub całkowicie niewykryte, gdy nazwisko było
  jednocześnie powszechnym słowem (np. „Wilk", „Vuk" = Wolf, „Vulpe" =
  Lis, „Sokol" = Sokół). Nazwisko jest teraz w pełni rozpoznawane.

- Nazwisko pod opisem „Nadawca" (polski), „Afsender" (duński) lub
  „Pošiljatelj" (słoweński) pozostawało częściowo lub całkowicie
  niewykryte, gdy nazwisko było jednocześnie powszechnym słowem (np.
  „Sowa" = Eule, „Bager" = Piekarz, „Volk" = Wolf). Nazwisko jest teraz w
  pełni rozpoznawane.

- Nazwisko pod opisem „Gavėjas" (litewski) lub „Prejemnik" (słoweński)
  pozostawało częściowo lub całkowicie niewykryte, gdy nazwisko było
  jednocześnie powszechnym słowem (np. „Vilkas" = Wilk). Podobnie jak
  wcześniej przy „Primatelj" (chorwacki) i „Modtager" (duński), nazwisko
  jest teraz w pełni rozpoznawane.

- Nagłówek okólnika, taki jak „To All Staff" lub „To All Employees", był
  błędnie rozpoznawany jako nazwisko osoby i usuwany. To teraz się nie
  zdarza.

- Nazwisko pod opisem „Primatelj" (chorwacki) lub „Modtager" (duński)
  pozostawało częściowo niewykryte, gdy nazwisko było jednocześnie
  powszechnym słowem (np. „Golub" = Gołąb, „Bager" = Piekarz). Podobnie
  jak wcześniej przy „Odbiorca" (polski) i „Destinatar" (rumuński),
  nazwisko jest teraz w pełni rozpoznawane.

- Pełne nazwisko w wierszu podpisu duńskiego, norweskiego lub greckiego
  dokumentu pozostawało częściowo niewykryte, gdy opis „Underskrift" lub
  „Υπογραφή" stał samodzielnie nad nazwiskiem – w przypadku greckim
  nazwisko było nawet rozpoznawane jako nazwa miejsca zamiast jako
  nazwisko. Podobnie jak wcześniej przy „Подпись" (rosyjski), nazwisko
  jest teraz w pełni rozpoznawane.

- Tekst na bocznie odłożonym zdjęciu z telefonu (zwykłe ujęcie pionowe,
  wyświetlane pionowo tylko dzięki znacznikowi obrotu obrazu) mógł zostać
  pominięty przez rozpoznawanie tekstu, ponieważ dotychczas odczytywano
  surowe, leżące piksele obrazu. Takie zdjęcia są teraz przed odczytem
  obracane we właściwą stronę – tak jak wcześniej już przy rozpoznawaniu
  twarzy.

- Pełne nazwisko w wierszu podpisu rosyjskiego, ukraińskiego lub
  litewskiego dokumentu pozostawało częściowo niewykryte, gdy opis
  „Подпись", „Підпис" lub „Parašas" stał samodzielnie nad nazwiskiem –
  imię lub imię odojcowskie odpadało. Podobnie jak wcześniej przy „Potpis"
  (chorwacki), nazwisko jest teraz w pełni rozpoznawane.

- Twarz na bocznie odłożonym zdjęciu z telefonu (zwykłe ujęcie pionowe,
  wyświetlane pionowo tylko dzięki znacznikowi obrotu obrazu) mogła zostać
  pominięta przez rozpoznawanie twarzy, ponieważ dotychczas sprawdzano
  surowe, leżące piksele obrazu. Takie zdjęcia są teraz przed
  wyszukiwaniem obracane we właściwą stronę.

- Pełne nazwisko w wierszu podpisu chorwackiego dokumentu pozostawało
  częściowo niewykryte, gdy opis „Potpis" stał samodzielnie nad nazwiskiem
  lub z dwukropkiem przed nim – imię odpadało, niezależnie od tego, czy
  jako własny wiersz, czy w „Potpis: Imię Drugie imię Nazwisko". Podobnie
  jak wcześniej przy „Unterschrift" i „Signature", nazwisko jest teraz w
  pełni rozpoznawane.

- Nazwisko małżeńskie za skrótami stanu cywilnego „verh." (zamężna/żonaty)
  i „verw." (owdowiała/owdowiały) pozostawało dotychczas w pełni
  niewykryte, niezależnie od tego, czy w nawiasie, po przecinku, czy
  bez spacji doklejone („Anna Meier (verh. Weber)", „Klaus Bauer
  (verw.Fischer)") – podobnie jak wcześniej przy „geb.", jest teraz
  niezawodnie rozpoznawane.

- Nazwisko za podpisem prokury „ppa." (np. w wierszu podpisu maila
  biznesowego lub listu biznesowego) pozostawało przy nazwisku zgodnym z
  nazwą zawodu, takim jak „Bauer" lub „Koch", dotychczas częściowo lub
  całkowicie niewykryte – podobnie jak wcześniej przy „gez.", jest teraz
  niezawodnie rozpoznawane.

- Numer polskiego dowodu osobistego był rozpoznawany tylko bez spacji
  między serią a numerem („ABS123456"). Dokument nie drukuje jednak w ten
  sposób tej wartości – urzędowo stoi tam spacja pomiędzy nimi
  („ABS 123456"), a w tej pisowni numer pozostawał dotychczas niewykryty.

- Animowany PNG (APNG, np. krótkie nagranie ekranu zapisane jako PNG
  zamiast GIF) był dotychczas sprawdzany i oczyszczany tylko z pierwszym
  obrazem, bez zgłaszania tego – podobnie jak wcześniej przy animowanym
  WebP, Maskuro zgłasza teraz, że każdy kolejny obraz pozostaje
  niesprawdzony w wyniku.

- Animowany obraz WebP (np. z narzędzia do zrzutów ekranu lub aplikacji
  czatu z wieloma obrazami w jednym pliku) był dotychczas sprawdzany i
  oczyszczany tylko z pierwszym obrazem, bez zgłaszania tego – podobnie
  jak wcześniej przy wielostronicowym TIFF, Maskuro zgłasza teraz, że
  każdy kolejny obraz pozostaje niesprawdzony w wyniku.

- Słoweńskie podwójne imię z łącznikiem („Ana-Marija Novak") traciło swoją
  przednią połowę, gdy tylko poprzedzał je w tekście ciąg zdaniowy – ten
  sam błąd co wcześniej przy polskim. „Ana-" pozostawało nieoczyszczone w
  czystym tekście, podczas gdy reszta nazwiska była już zastępowana.

- Polskie podwójne imię z łącznikiem („Anna-Maria Kowalska") traciło swoją
  przednią połowę, gdy tylko poprzedzał je w tekście ciąg zdaniowy lub
  przyimek, taki jak „z"/„od" – reszta nazwiska była zastępowana, „Anna-"
  pozostawało nieoczyszczone w czystym tekście.

- Kazachskie formy grzecznościowe „Хабарласыңыз"/„Байланысыңыз" (proszę się
  skontaktować) oraz serbskie formy czasownikowe „Помоћи", „Чекамо" i
  „Пишите" bez własnego modelu rozpoznawania języka były w zdaniach
  telefonicznych błędnie rozpoznawane jako nazwisko osoby lub miejsce.

- Azerbejdżańskie słowo grzecznościowe „Xahiş" (Proszę/Uprasza się) bez
  własnego modelu rozpoznawania języka było w zdaniach telefonicznych
  błędnie rozpoznawane jako nazwisko osoby.

- Indonezyjskie i malajskie słowa grzecznościowe/wzywające bez własnego
  modelu rozpoznawania języka, takie jak „Silakan", „Mohon" (indonezyjski),
  „Sila" i „Tolong" (malajski), były w zdaniach telefonicznych błędnie
  rozpoznawane jako nazwisko osoby lub miejsce.

- Uzbecka forma wzywająca „Kutamiz" (czekamy) bez własnego modelu
  rozpoznawania języka była w zdaniach telefonicznych błędnie rozpoznawana
  jako miejsce.

- Tureckie formy wzywające bez własnego modelu rozpoznawania języka, takie
  jak „Arayınız" (proszę zadzwonić) i „Bekliyoruz" (czekamy), były w
  zdaniach telefonicznych błędnie rozpoznawane jako nazwisko osoby.

- Formy wzywające w kolejnych językach bez własnego modelu rozpoznawania
  języka (czeski, słowacki, grecki), takie jak „Zavolejte" (zadzwoń),
  „Prosíme" (prosimy) i „Περιμένουμε" (czekamy), były w zdaniach
  telefonicznych błędnie rozpoznawane jako nazwisko osoby lub miejsce.

- Węgierskie i polskie formy wzywające, takie jak „Hívjon" (zadzwoń),
  „Kérjük" (prosimy), „Várjuk" (oczekujemy), „Zadzwoń" i „Czekamy", były w
  zdaniach telefonicznych błędnie rozpoznawane jako nazwisko osoby lub
  miejsce.

- W numerowanej liście nazwisk bez formy tabelarycznej (np. „1. Robert
  Brown", pod spodem „2. Mary Johnson") nazwisko z pewnymi angielskimi
  nazwiskami (m.in. „Brown", „White", „Green", „Black", „Young") było
  całkowicie pomijane – model językowy doklejał numer następnego wiersza
  do nazwiska, przez co trafienie nigdy dokładnie nie pasowało.

- W polskim modelu językowym poprzedzający inicjał imienia przed
  nazwiskiem (np. „J. Kowalski", „A. Nowak") pozostawał nierozpoznany i
  nieoczyszczony w tekście – zastępowane było tylko nazwisko. Inne
  sprawdzane języki (m.in. niemiecki, angielski, rumuński, chorwacki,
  węgierski, rosyjski) uwzględniały ten sam inicjał już wcześniej.

- Nazwisko osoby za pisanym małą literą tytułem, takim jak „dr.", „ing."
  lub „dipl. ing.", nie było w ogóle rozpoznawane po węgiersku, rumuńsku i
  chorwacku – ginął nie tylko tytuł, ale całe nazwisko
  (np. „dr. Kovács Béla", „ing. Andrei Popescu", „dipl. ing. Marko
  Horvat").
- W słoweńskich protokołach posiedzeń samo oznaczenie roli przed
  dwukropkiem (np. „Tajnik:", „Podpredsednik:", „Poročevalec:",
  „Predsedujoči:") było błędnie rozpoznawane jako nazwisko osoby, gdy tylko
  w innym miejscu protokołu stało już prawdziwe nazwisko mówcy.
- W rosyjskich protokołach posiedzeń samo oznaczenie roli przed dwukropkiem
  (np. „Секретарь:", „Докладчик:", „Докладчица:") było błędnie
  rozpoznawane jako nazwisko osoby, gdy tylko w innym miejscu protokołu
  stało już prawdziwe nazwisko mówcy.
- W rumuńskich protokołach posiedzeń samo oznaczenie roli z rodzajnikiem
  określonym przed dwukropkiem (np. „Secretarul:", „Președintele:",
  „Vicepreședintele:", „Moderatorul:", „Consilierul:") było błędnie
  rozpoznawane jako nazwisko osoby – „Președintele" już samo w sobie,
  pozostałe dodatkowo, gdy tylko w innym miejscu protokołu stało już
  prawdziwe nazwisko mówcy.
- W chorwackich protokołach posiedzeń samo oznaczenie roli przed
  dwukropkiem (np. „Izvjestiteljica:", „Zapisničar:"/„Zapisnicar:",
  „Predsjedavajući:") było błędnie rozpoznawane jako nazwisko osoby.
- Polski adres skrytki pocztowej „Skrytka pocztowa" za opisem nadawcy lub
  odbiorcy (np. „Odbiorca: Skrytka pocztowa 45") był błędnie rozpoznawany
  jako nazwisko osoby.
- Chorwacki adres skrytki pocztowej „Poštanski pretinac" za opisem adresu
  „Adresa:" (np. „Adresa: Poštanski pretinac 45", również z doklejonym
  „br." dla numeru) był błędnie rozpoznawany jako nazwisko osoby.
- Miejscowość bez dalszego opisu w norweskim tekście ciągłym (np. „Anna
  Hansen bor i Oslo") nie była rozpoznawana – własny model językowy
  nazywa tam miejsca zazwyczaj własną, dotychczas nieprzyporządkowaną
  etykietą zamiast zwykłego „LOC".
- Data w kolejności ISO rok-miesiąc-dzień z łącznikiem lub kropką (np.
  „2024-12-31") nie była w niektórych językach w ogóle rozpoznawana jako
  data – najbardziej widoczne po litewsku, gdzie pisma urzędowe podają
  daty przeważnie w tej kolejności.
- Węgierski numer VAT (közösségi adószám) w urzędowo równie ważnej formie
  bez separatorów, 11-cyfrowej (np. „12345678123" zamiast
  „12345678-1-23"), nie był rozpoznawany.
- Polski numer identyfikacji podatkowej NIP z separatorami w grupowaniu
  3-2-2-3 (np. „856-73-46-215", jak zwykle na fakturach firm i
  jednoosobowych działalności gospodarczych) nie był rozpoznawany – trafiało
  tylko grupowanie 3-3-2-2 dla osób fizycznych.
- Nazwa firmy pod słowackim opisem pola „Zamestnávateľ:" lub
  „Názov zamestnávateľa:" (pracodawca/firma) nie była rozpoznawana.
- Nazwa firmy pod rumuńskim opisem pola „Angajator:" lub „Denumire
  angajator:" (pracodawca/firma) nie była rozpoznawana.
- Nazwa firmy pod węgierskim opisem pola „Cég:" lub „Munkáltató:"
  (firma/pracodawca) nie była rozpoznawana.
- Nazwa firmy pod polskim opisem pola „Pracodawca:" lub „Nazwa firmy:"
  (pracodawca/firma) nie była rozpoznawana.
- Nazwa firmy pod słoweńskim opisem pola „Podjetje:" lub „Delodajalec:"
  (firma/pracodawca) nie była rozpoznawana.
- Nazwa firmy pod chorwackim opisem pola „Tvrtka:" lub „Poslodavac:"
  (firma/pracodawca) nie była rozpoznawana.
- Kwota pieniężna wypisana słownie z walutą pisaną małą literą (np.
  „500 euro") nie była rozpoznawana, trafiała tylko pisownia wielką literą
  („Euro").
- Nazwisko za „Schwager"/„Schwägerin" (szwagier/szwagierka; np. „Der
  Schwager Bauer erhält die Erbschaft.") nie było rozpoznawane.
- Przy tureckim adresie bez znaku interpunkcyjnego oddzielającego między
  kodem pocztowym+miejscowością a ulicą+numerem domu (np. „34000 İstanbul
  İstiklal Caddesi No: 45") numer domu pozostawał nieoczyszczony.
- Przy słowackim adresie bez znaku interpunkcyjnego oddzielającego między
  kodem pocztowym+miejscowością a ulicą+numerem domu (np. „831 01
  Bratislava Hlavná 15") numer domu pozostawał nieoczyszczony.
- Kraj urodzenia bez dalszego opisu w chorwackim polu formularza (np.
  „Zemlja rođenja: Njemačka") nie był rozpoznawany.
- Kraj urodzenia bez dalszego opisu w litewskim polu formularza (np.
  „Gimimo valstybė: Vokietija") nie był rozpoznawany.
- Kraj urodzenia lub zamieszkania bez dalszego opisu w polskim polu
  formularza (np. „Kraj: Niemcy") nie był rozpoznawany.
- Miejscowość obywatelstwa lub zamieszkania bez dalszego opisu w
  słoweńskim polu formularza (np. „Državljanstvo: Nemčija") nie była
  rozpoznawana.
- Kraj zamieszkania bez dalszego opisu w norweskim polu formularza (np.
  „Bosted: Tyskland") nie był rozpoznawany.
- Nowa strona ustawień „Powiadomienia" (wcześniej sekcja w „Program"):
  trzy powiadomienia paska zadań (podgląd gotowy, przetwarzanie ukończone,
  aktualizacja pobrana) mają teraz własne miejsce.
- Nowość: wynik można dodatkowo zapisać jako czysty plik tekstowy (.txt)
  lub z rozszerzeniem .md obok – do dalszego przetwarzania w AI lub innym
  programie.
- Przy chorwackim wpisie kontaktowym z opisem „Osoba za kontakt"/„Kontakt
  osoba" (np. „Osoba za kontakt: Golub Marko") nazwisko pozostawało w
  pełni niewykryte, gdy nazwisko było jednocześnie powszechnym
  rzeczownikiem (Golub = „Gołąb").

- Przy rumuńskim wpisie kontaktowym z opisem „Persoana de contact"/
  „Persoană de contact" (np. „Persoana de contact: Lup Ion") nazwisko
  pozostawało w pełni niewykryte, gdy nazwisko było jednocześnie
  powszechnym rzeczownikiem (Lup = „Wilk"), a imię bardzo krótkie i
  ogólne.

- Przy polskim wpisie kontaktowym z opisem „Osoba kontaktowa"/„Osoba do
  kontaktu" (np. „Osoba kontaktowa: Wilk Adam") nazwisko pozostawało
  niewykryte, gdy było jednocześnie powszechnym rzeczownikiem (Wilk =
  „Wolf", Zielony = „grün").

- Przy rumuńskim adresie bez znaku interpunkcyjnego oddzielającego między
  kodem pocztowym+miejscowością a ulicą+numerem domu (np. „010061
  București Strada Victoriei 30") numer domu pozostawał nieoczyszczony.
- Przy serbskim adresie bez znaku interpunkcyjnego oddzielającego między
  kodem pocztowym+miejscowością a ulicą+numerem domu (np. „11000 Beograd
  Bulevar Kralja Aleksandra 73") numer domu pozostawał nieoczyszczony.
- Przy greckim adresie bez znaku interpunkcyjnego oddzielającego między
  kodem pocztowym+miejscowością a ulicą+numerem domu (np. „104 32 Αθήνα
  Ερμού 15") numer domu pozostawał nieoczyszczony.
- Przy słoweńskim adresie bez znaku interpunkcyjnego oddzielającego między
  kodem pocztowym+miejscowością a ulicą+numerem domu (np. „1000 Ljubljana
  Slovenska cesta 58") kod pocztowy pozostawał nieoczyszczony.
- Przy litewskim adresie bez znaku interpunkcyjnego oddzielającego między
  kodem pocztowym+miejscowością a ulicą+numerem domu (np. „LT-01100
  Vilnius Gedimino pr. 9") kod pocztowy pozostawał w pełni nieoczyszczony.
- Przy węgierskim adresie bez znaku interpunkcyjnego oddzielającego między
  kodem pocztowym+miejscowością a ulicą+numerem domu (np. „1052 Budapest
  Kossuth Lajos utca 12") kod pocztowy pozostawał nieoczyszczony.
- Nazwisko za „Erben" (spadkobiercy; np. „Die Erben Wagner erhielten die
  Mitteilung fristgerecht.") pozostawało w kontekście dziedziczenia/spadku
  niemal zawsze niewykryte.
- Nazwisko za „Geschwister" (rodzeństwo; np. „Die Geschwister Bauer wohnen
  in Linz.") pozostawało dotychczas niemal zawsze niewykryte – w
  odróżnieniu od „Familie"/„Ehepaar" dotyczyło to nie tylko nazwisk
  zgodnych z nazwą zawodu (Koch, Bauer, Richter), ale dowolnych nazwisk w
  tym miejscu.
- Nazwisko za „Ehepaar" lub „Eheleute" (małżeństwo; np. „Das Ehepaar Koch
  zieht um.") pozostawało niewykryte, gdy było jednocześnie powszechnym
  rzeczownikiem lub nazwą zawodu (Koch, Bauer, Richter).
- Zwykły numer zamówienia, zlecenia lub artykułu w typowym grupowaniu
  numeru podatkowego lub numeru ubezpieczenia społecznego (np. „030 4471
  2298") był bez żadnego przypisanego opisu błędnie zaczerniany jako taki
  numer.
- Numer dowodu/procesu w formacie „rok/numer bieżący" (np. w „Rechnung Nr.
  4/2024/778899") był przez rozpoznawanie numerów telefonu błędnie
  zaczerniany jako numer telefonu.
- Nazwisko za „Herr"/„Frau" z wielosłownym łańcuchem tytułów akademickich
  przed nim („Herr Dr. med. Weber", „Herr Prof. Dr. Krause") pozostawało
  dotychczas w pełni bez ochrony – rozpoznawane było dotychczas tylko
  pojedyncze słowo tytułu między zwrotem grzecznościowym a nazwiskiem.
- Sygnatura akt sądowych w klasycznym formacie ze skrótem izby/senatu
  („4 Ca 1523/24", „Az.: 7 O 234/25") pozostawała dotychczas w pełni bez
  ochrony – nie rozpoznawana była też zwykła skrócona forma „Az."/„Gz."
  obok wypisanego opisu.
- Numer karty kredytowej rozdzielony w środku swojego czterocyfrowego
  grupowania złamaniem wiersza – np. w wąskiej kolumnie tabeli – pozostawał
  dotychczas w pełni bez ochrony.
- Numer identyfikacji podatkowej rozdzielony w środku swojego grupowania
  złamaniem wiersza – np. w wąskiej kolumnie tabeli lub polu formularza –
  pozostawał dotychczas w pełni bez ochrony.
- Numer ubezpieczenia społecznego rozdzielony w środku swojego grupowania
  złamaniem wiersza – np. w wąskiej kolumnie tabeli – pozostawał
  dotychczas w pełni bez ochrony, nawet nie częściowo zastąpiony.
- Numer domu z zakresem, taki jak „12a-14b" lub „3-5", był zastępowany
  tylko w połowie – druga część za łącznikiem pozostawała otwarcie
  widoczna w wyniku.
- Numer nadwozia (FIN/VIN) rozdzielony w środku swoich 17 znaków złamaniem
  wiersza, spacją lub łącznikiem – np. w wąskiej kolumnie tabeli lub polu
  dowodu rejestracyjnego – pozostawał dotychczas w pełni bez ochrony.
- Zwrot w liście/mailu, taki jak „Liebe Anna!" lub „Lieber Hans" – bez
  przecinka po nazwisku, najczęstsza forma w swobodnych mailach –
  pozostawiał nazwisko w pełni bez ochrony, również w pełnym dokumencie z
  tekstem ciągłym i formułą pożegnalną pod spodem.
- Ta sama luka dotyczyła również swobodnych zwrotów czatu/maila „Hallo
  Anna!", „Hi Anna!", „Hey Anna!" i „Servus Anna!" bez przecinka –
  nazwisko pozostawało również w pełni bez ochrony.
- Sam blok podpisu, który zaczyna się bezpośrednio od „MfG" lub
  „Herzlichst" – np. skopiowany ze schowka, bez poprzedzającego zdania –
  pozostawiał nazwisko pod nim w pełni bez ochrony.
- Pole z kilkoma osobami, np. „Angehörige: Kaczmarek, Piotr (Sohn),
  Kaczmarek, Anna (Ehefrau)", zlewało oba nazwiska wraz z dopiskiem w
  nawiasie w jedno, zbyt długie trafienie – drugie nazwisko pozostawało
  przy tym częściowo bez ochrony w wyniku.
- Ulica bez przyrostka „-straße"/„-weg" – jak to zwykle bywa na wsi, np.
  „Am Marktplatz 5" lub „Im Grund 12" – nie była rozpoznawana, gdy
  następował po niej wiersz kod pocztowy-miejscowość, np. w zaświadczeniu
  o zameldowaniu: „Neue Anschrift: Am Weidengarten 17, 54295 Trier"
  traciło ulicę w pełni, usuwany był tylko kod pocztowy.
- Nazwisko za złożonym opisem pola z ukośnikiem (np. „Name/Vorname: Bauer
  Klaus") było częściowo nierozpoznawane – wieloznaczne nazwisko, takie
  jak „Bauer", pozostawało bez odpowiedniego dowodu pola niewykryte. Ta
  sama luka dotyczyła pól łączonych, takich jak „PLZ/Ort: 04109 /
  Leipzig". To samo dotyczyło pól łączonych z wypisanym łącznikiem zamiast
  ukośnika, np. „Vor- und Nachname: Bauer Klaus" lub „Nachname bzw.
  Vorname: …".
- Data urodzenia w formie „Datum der Geburt: …" oraz data zgonu w formie
  „Todesdatum: …" lub „Datum des Todes: …" nie były rozpoznawane –
  trafiały tylko „Geburtsdatum: …" lub „Sterbedatum: …".
- Data ślubu w formie „Datum der Heirat: …" lub „Datum der Hochzeit: …"
  nie była rozpoznawana – trafiały tylko „Hochzeitsdatum: …",
  „Heiratsdatum: …" i „Datum der Eheschließung: …", chociaż data rozwodu,
  naturalizacji i zawarcia związku partnerskiego znały tę samą formę
  „Datum der X" od dawna.
- Data rozwodu w formie „Datum der Scheidung: …" nie była rozpoznawana –
  trafiały tylko „Scheidungsdatum: …" i postpozycyjna forma czasownikowa,
  chociaż data naturalizacji i zawarcia związku partnerskiego znały tę
  samą formę „Datum der X" od początku.
- Data zawarcia związku partnerskiego nie była dotychczas w ogóle
  rozpoznawana – ani z opisem („Verpartnerungsdatum: …", „Datum der
  Lebenspartnerschaft: …"), ani w tekście ciągłym („… wurden am …
  verpartnert"). Jest teraz zastępowana jako osobny rodzaj danych, tak jak
  data urodzenia, ślubu, rozwodu i naturalizacji.
- Data naturalizacji nie była dotychczas w ogóle rozpoznawana – ani z
  opisem („Einbürgerungsdatum: …"), ani w tekście ciągłym („… wurde am …
  eingebürgert"). Jest teraz zastępowana jako osobny rodzaj danych, tak
  jak data urodzenia, ślubu i rozwodu.
- Data rozwodu nie była dotychczas w ogóle rozpoznawana – ani z opisem
  („Scheidungsdatum: …"), ani w tekście ciągłym („Die Ehe wurde am …
  geschieden"). Jest teraz zastępowana jako osobny rodzaj danych, tak jak
  data urodzenia, zgonu i ślubu.
- Data ślubu za genealogicznym znakiem ślubu „⚭" bez opisu nie była
  rozpoznawana, chociaż data urodzenia i zgonu w tym samym wierszu przez
  gwiazdkę i krzyżyk były już rozpoznawane – teraz rozpoznawana jest
  również data ślubu.
- Data zgonu za krzyżykiem klepsydry bez opisu („*03.06.1940
  †21.11.2023") nie była rozpoznawana, chociaż data urodzenia przed nią
  była już rozpoznawana przez genealogiczną gwiazdkę – teraz rozpoznawana
  jest również data zgonu.
- Nazwisko przed imieniem na końcu wiersza tematu/zgłoszenia z
  poprzedzającym tekstem rzeczowym i łącznikiem („Betreff: Reklamation -
  Bauer, Anna") nie było rozpoznawane przy nazwisku zgodnym z nazwą
  zawodu – jest teraz rozpoznawane.
- Numery kandydatów i wnioskodawców za swoim opisem („Bewerbernummer:
  4471829", „Antragstellernummer: 7654321") całkowicie umykały
  rozpoznawaniu – są teraz rozpoznawane.
- Zastępowanie nie zaczernia już, gdy nie ma miejsca na czytelny symbol
  zastępczy – zbyt mały symbol zastępczy jest teraz zapisywany mniejszą
  czcionką zamiast stawać się pustym paskiem, dopóki w ogóle zostaje
  miejsce. Nowość ponadto: czy miejsce trafienia na obrazie (nagłówek
  listu, tło skanu) jest opisane, czy tylko zaczernione, można teraz
  ustawiać niezależnie od pozostałego rodzaju wyniku. A miejsce trafienia
  na obrazie, który jest całkowicie usuwany, było opisywane, jakby obraz
  pozostawał – symbol zastępczy stał jasny na tle, które nigdy nie było
  zaczerniane, i tym samym znikał niewidocznie na teraz białym papierze.
- Miejsce trafienia na **zachowanym** obrazie było przy zastępowaniu
  zawsze zaczerniane czarno-biało, niezależnie od wybranej prezentacji
  (kolory kategorii, tęcza …) – widoczne jako złamanie między kolorowymi
  etykietami w tekście ciągłym a czarnymi paskami na nagłówku listu. Tło
  obrazu podąża teraz za tym samym kolorem, co symbol zastępczy obok.
- Rozpoznawanie numeru identyfikacyjnego pojazdu (FIN/VIN) oznaczało każdy
  17-znakowy alfanumeryczny kod bez I/O/Q bezwarunkowo jako numer
  nadwozia – również numery zlecenia, serii i klucza licencyjnego, które
  przypadkowo mają tę samą formę. Teraz liczy się tylko ze słowem
  kontekstowym w pobliżu („FIN", „VIN", „Fahrgestell", „Chassis" itp.).
- W systemach ticketowych/kalendarzowych rozpoznawanie nazwisk wciągało po
  „Assigned to"/„Closed by" itp. następne słowo pola, gdy stało bez
  separatora bezpośrednio w tym samym wierszu („Assigned to Max
  Mustermann Priority High" stawało się „Max Mustermann Priority"). W
  nagłówkach commitów Git rozpoznawanie nazwisk wciągało podobnie
  **następny** klucz trailer, gdy dwa wiersze łączyła tylko jedna spacja
  zamiast złamania wiersza („Author: julia bergmann Reviewed-by: …"
  stawało się „julia bergmann Reviewed-by"). Dodano oba hamulce.
- Nazwisko za „p.A.", „zH"/„zHd", „i.A."/„i.V." i „geb." wciągało
  bezpośrednio następujące słowo działu w to samo trafienie, gdy stało bez
  separatora w tym samym wierszu („p.A. Max Mustermann Buchhaltung"
  stawało się „Max Mustermann Buchhaltung", „i.A.Max Mustermann
  Vertrieb" – „Max Mustermann Vertrieb"). Ten sam hamulec co przy
  „Assigned to"/trailerach Git dodano teraz również tutaj.
- Opisany IBAN bezpośrednio nad wierszem BIC, BLZ lub SWIFT wciągał opis
  tego wiersza we własne trafienie, ponieważ „BIC" i „BLZ" same wyglądały
  jak kolejny blok numeru – z „IBAN: DE89 … 0130 00" i wiersza pod nim
  powstawało jedno, zbyt daleko sięgające trafienie, a opis następnego
  wiersza znikał razem z oczyszczaniem. Dotyczyło to niemal każdego
  połączenia bankowego z IBAN i BIC jeden pod drugim.
- Panel trafień pokazuje teraz, **gdzie** znajduje się symbol zastępczy,
  którego nie może odnaleźć na stronie. Dwa przypadki dotychczas
  zgłaszały tylko „nie znaleziono", mimo że zastąpienie miało miejsce.
  Jeśli symbol zastępczy stoi w niewidocznym tekście pobocznym – np. w
  adresie odnośnika, adnotacji lub polu formularza – wiersz niesie to
  teraz jako osobną informację („w tekście pobocznym"), a kliknięcie to
  wyjaśnia. A jeśli symbol zastępczy był z braku miejsca zapisany
  skrócony („[N382]" zamiast „[NAM382]"), kliknięcie w długi wiersz
  przeskakuje teraz do miejsca skróconej formy i nazywa zmianę nazwy;
  przypisanie łączy przy tym oba wiersze wyraźnie ze sobą.
- Jeśli ta sama wartość zastępcza stoi w dokumencie wielokrotnie, każde
  kolejne kliknięcie w wiersz panelu skacze w kółko do następnego miejsca
  trafienia – również przez granice stron; wiersz stanu liczy razem
  („Miejsce trafienia 2 z 4"), a aktualnie wskazywane miejsce jest
  wyraźniej obramowane niż pozostałe. A gdy symbol zastępczy stoi tylko
  na liście trafień, ale nigdzie w dokumencie (ponieważ miejsce zostało
  wchłonięte przez nakładające się zastąpienie), wiersz stanu mówi to
  teraz, zamiast żeby kliknięcie pozostawało nieme i bez skutku.
- Skrócone imię za „an" lub „für" jest teraz niezawodnie rozpoznawane jako
  nazwisko – „Überweisung an M. Wagner" i „Rechnung für M. Wagner"
  pozostawały dotychczas często nieoczyszczone, podczas gdy to samo
  nazwisko z innym opisem przed nim (np. „Zahlungsempfänger:") było już
  znajdowane. Dotyczyło to głównie wierszy wyciągu z konta i księgowań.
- „Angeklagter"/„Angeklagte"/„Beschuldigter"/„Beschuldigte" (oskarżony/
  oskarżona) liczą się teraz jako pole nazwiska: gdy nazwisko stało w
  pismach postępowania karnego bezpośrednio za jednym z tych opisów, było
  dotychczas dla mniej więcej połowy sprawdzanych nazwisk w ogóle
  nierozpoznawane – ani imię, ani nazwisko.
- Miejsce klikane w panelu trafień jest teraz obramowane na niebiesko
  zamiast oznaczone żółto – na kolorowych powierzchniach sygnalizacji
  kontrolnej żółty kolor trafień wyszukiwania nie był rozpoznawalny.
  Ponadto kliknięcie znajduje teraz również wielosłowne wartości
  zastępcze (zmyślone nazwiska, zamaskowane numery): dotychczas
  pozostawało przy takich wierszach bezskuteczne, ponieważ miejsce
  trafienia było szukane słowo po słowie.
- Rodzice adopcyjni, zastępczy i przybrani („Adoptivvater", „Pflegemutter",
  „Stiefvater" i inne) są teraz rozpoznawani jako pole nazwiska, nazwisko
  wcześniej przechodziło przez rozpoznawanie nieoczyszczone
- Tabele i listy bogate w liczby nie są już błędnie odrzucane: gdy krótka
  liczba (np. część numeru klienta odczytana jako numer telefonu) była
  zastępowana, kontrola końcowa zgłaszała ten sam ciąg cyfr jako
  pozostałe dane, nawet gdy przypadkowo pojawiał się gdzie indziej w
  zupełnie innym numerze – i wtedy nie dostarczała żadnego wyniku. Liczba
  liczy się teraz jako pozostałość tylko tam, gdzie stoi jako osobna
  liczba.
- Akty stanu cywilnego: „Vater:"/„Mutter:" (Ojciec/Matka) jest teraz
  rozpoznawane jako pole nazwiska, nazwisko rodzica wcześniej przechodziło
  przez rozpoznawanie nieoczyszczone
- Kolejne role rodzinne („Pate", „Großvater/-mutter", „Ehepartner",
  „Lebenspartner", „Onkel", „Tante" – chrzestny, dziadek/babcia, małżonek,
  partner życiowy, wujek, ciocia) są teraz rozpoznawane jako pole
  nazwiska, nazwisko wcześniej przechodziło przez rozpoznawanie
  nieoczyszczone
- Niemiecki numer rozliczeniowy banku jest teraz rozpoznawany również w
  urzędowym grupowaniu ("370 400 44", "370.400.44", "370-400-44",
  "370/400/44"), nie tylko jako osiem połączonych cyfr.
- Niemiecki numer ubezpieczenia rentowego jest teraz rozpoznawany również
  z kropką, łącznikiem lub ukośnikiem między pięcioma blokami
  ("65-170839-J-08-8", "65.170839.J.08.8"), nie tylko ze spacją.
- Okno główne pojawia się szybciej: biblioteki rozpoznawania (Presidio
  wraz z podbudową modelu językowego) były dotychczas ładowane już przy
  budowie okna – w Windows około cztery sekundy, zanim w ogóle było cokolwiek
  widać. Teraz ładują się w pełni w tle; przycisk „Oczyść" staje się jak
  dotychczas dostępny dopiero, gdy wszystko jest gotowe.
- Dokumenty Office z wieloma obrazami lub filmami są zapisywane szybciej:
  już skompresowane media są zapisywane w pakiecie wynikowym zamiast
  bezużytecznie kompresowane po raz drugi – to dotychczas nie oszczędzało
  ani jednego bajta i raczej powiększało pliki JPEG.
- Arkusze kalkulacyjne i inne dokumenty złożone z wielu małych jednostek
  tekstu są sprawdzane szybciej: rozpoznawanie języka przetwarza teraz
  wszystkie komórki i akapity dokumentu w jednym przebiegu zamiast
  pojedynczo – przy udowodnionych tych samych trafieniach (400 komórek: z
  ok. 4,7 do 2,5–3,5 sekundy).
- Strony PDF przypominające listy (spisy, listy pozycji) są przy
  wstawianiu symboli zastępczych wyraźnie szybsze: wyszukiwanie miejsca
  dla każdego opisu przebiegało dotychczas przez wszystkie słowa strony –
  teraz tylko przez otoczenie wiersza, przy udowodnionym tym samym wyniku
  (na stronie z 300 opisami około szesnastokrotnie szybciej).
- Dokumenty bogate w obrazy oszczędzają kilka niepotrzebnych kroków
  roboczych na obraz: liczenie twarzy i kodów na stronach PDF nie
  dekoduje już obrazu strony podwójnie, sprawdzanie metadanych nie
  odszyfrowuje już w ogóle czystego obrazu, spikselowane obrazy są
  zapisywane ze zwykłą zamiast najwolniejszej kompresją PNG (ten sam
  rozmiar, jedna trzecia czasu), a bez ustawionego znaku wodnego odpada
  bezużyteczne ponowne zapisywanie całego PDF na końcu.
- Zeskanowane pliki PDF z włączonym rozpoznawaniem tekstu są wyraźnie
  szybciej przetwarzane: każda strona była dotychczas renderowana dwukrotnie
  w pełnej rozdzielczości (raz do odczytu, raz do rastrowania) – obraz jest
  teraz ponownie wykorzystywany. A na Windows/Linux rozpoznawanie tekstu
  odczytuje paski dużego skanu w jednym przebiegu zamiast z własnym
  uruchomieniem programu na pasek.
- Duże dokumenty są oczyszczane wyraźnie szybciej: porównywanie już
  znalezionych wartości rosło dotychczas wraz z liczbą miejsc trafień
  (blok tekstu 64 KB kosztował na końcu dużego pliku około sekundy tylko
  na to, teraz jedną sześćdziesiątą), a wyszukiwanie form prawnych firm
  przebiegało z wszystkimi ~280 formami katalogu przez każde miejsce
  tekstu (teraz około dwadzieścia razy szybciej, przy udowodnionych tych
  samych trafieniach).
- Nazwisko bezpośrednio po „Beste Grüße"/„Beste Wünsche" bez poprzedzającego
  tekstu lub znaku interpunkcyjnego nie było w ogóle rozpoznawane – sam
  blok podpisu bez tekstu ciągłego przed nim sprawiał, że nazwisko
  znikało bez śladu.
- Pole adresu na początku dokumentu z nazwiskiem zgodnym z nazwą zawodu
  („Bauer Anna", „Koch Stefan" jako pierwszy wiersz nad ulicą i
  miejscowością) pozostawało dotychczas częściowo nierozpoznane lub było
  klasyfikowane jako nazwa miejsca zamiast osoby – bez poprzedzającego
  zdania modelowi językowemu brakowało budowy zdania, która inaczej
  pozwala rozpoznać „Bauer" jako nazwisko, a nie jako zawód.
- Nazwisko za znacznikiem podpisu „gez." z nazwiskiem zgodnym z nazwą
  zawodu przed imieniem („gez. Bauer Anna" na końcu decyzji lub wyroku)
  pozostawało dotychczas rozpoznane niekompletnie – znajdowane było tylko
  imię, nazwisko znikało bez śladu.
- Nazwisko bezpośrednio za numerem klienta, umowy lub podobnym numerem
  identyfikacyjnym bez własnego wiersza („Vertragsnummer 55219 Bauer
  Anna", „Kundennr. 4711 Bauer Anna") było przy nazwisku zgodnym z nazwą
  zawodu dotychczas niekompletnie lub wcale nierozpoznawane.
- Symbol na pasku menu macOS jest teraz szablonem, który dostosowuje się
  jak sąsiednie symbole do trybu jasnego i ciemnego – dzięki dwóm
  wyciętym paskom pozostaje przy tym rozpoznawalny jako Maskuro. Gdy działa
  strażnik schowka, pokazuje to odsunięta kropka przy czubku tarczy.
- Kliknięcie w panelu trafień prowadzi teraz również w trybie
  anonimizującym do miejsca trafienia: zmiana strony, przewinięcie do
  obrazu, żółte oznaczenie. Dotychczas kliknięcie pozostawało tam bez
  skutku, ponieważ uznawało symbole zastępcze wciąż za bez numerów –
  odkąd każde miejsce trafienia ma własny numer, miejsce jest
  jednoznaczne. Tylko przy rzeczywiście bez numerach symbolu zastępczym
  wiersz stanu nadal wyjaśnia, dlaczego nie można ustalić celu skoku.
- Pierwsze zapisanie w edytorze poprawek (Ctrl+S lub przycisk dyskietki)
  pyta teraz o miejsce, jak „Zapisz jako …" – wstępnie ustawione na folder
  oryginału i nazwę wyniku. Dotychczas plik lądował bez słowa obok
  oryginału. Kto wcześniej już wybrał miejsce zapisu przez wiersz stanu,
  nie jest pytany ponownie; każde kolejne zapisanie zapisuje jak
  dotychczas ten sam plik dalej.
- Jeśli kontrola bezpieczeństwa przed zapisem zgłasza podejrzane miejsce,
  „Powrót do kontroli" prowadzi teraz do niego: pierwsze miejsce trafienia
  przewija się do widoku i jest obramowane na czerwono, wiersz stanu je
  nazywa. Dotychczas pozostawano samemu z numerem strony i współrzędnymi
  punktu. Z okna głównego otwiera się w tym celu edytor w tym miejscu.
  Również przy wskazówce o odbiegającej liczbie stron przycisk prowadzi
  teraz do celu – do pierwszej strony, która istnieje tylko w jednym z
  obu dokumentów.
- Kto przełącza podgląd na „Obok siebie w dwóch kolumnach", dostaje teraz
  automatycznie okno, w które pasują obie kolumny – dotychczas ściskały
  się w starej szerokości, dopóki się samemu nie pociągnęło. Poszerzanie
  następuje najwyżej do krawędzi ekranu i nigdy nie zwęża się z powrotem;
  samodzielnie ustawiona szerokość pozostaje.
- Nazwisko i imię w oddzielnych kolumnach tabeli (np. „Nazwisko | Imię" w
  potwierdzeniu zgłoszenia lub eksporcie CSV) pozostawały otwarte – każda
  komórka sama w sobie wyglądała dla rozpoznawania jak dowolne słowo bez
  związku z nazwiskiem. Są teraz rozpoznawane.
- Nazwisko i imię na tylnej stronie karty prawa jazdy UE pozostawały
  otwarte – stoją tam za urzędowymi kodami pól „1." i „2." zamiast za
  niemieckim słowem, i właśnie to sprawiało, że pozostawały niewykryte.
  Są teraz rozpoznawane, gdy obok stoi numer prawa jazdy (kod pola „5.").
- Imię posiadacza pojazdu w dowodzie rejestracyjnym pozostawało otwarte –
  stoi za urzędowym kodem pola „C.1.2" zamiast za niemieckim słowem, takim
  jak „Vorname", i właśnie to sprawiało, że pozostawało niewykryte.
  Nazwisko i imię pod kodami pól C.1, C.1.1 i C.1.2 są teraz rozpoznawane.
- Pierwszy wiersz strefy odczytu maszynowego (MRZ) na paszporcie lub
  dowodzie osobistym pozostawał otwarty – niesie nazwisko w formacie
  „NAZWISKO<<IMIĘ" i przechodził przez rozpoznawanie nawet z nowym
  rozpoznawaczem MRZ dla wiersza cyfry kontrolnej. Trafienie liczy się
  teraz tylko wtedy, gdy bezpośrednio obok stoi drugi wiersz MRZ ważny pod
  względem cyfry kontrolnej – sam wiersz nazwiska nie ma własnej cyfry
  kontrolnej.
- Drugi wiersz strefy odczytu maszynowego (MRZ) na paszporcie lub dowodzie
  osobistym pozostawał całkowicie niewykryty – zawiera numer paszportu,
  datę urodzenia i datę ważności w czystym tekście, ale nie trafiał w
  żaden istniejący rozpoznawacz. Własny rozpoznawacz sprawdza teraz cztery
  cyfry kontrolne ICAO.
- Tablica rejestracyjna bez żadnej spacji do opisu pozostawała otwarta –
  „KennzeichenM-AB1234" lub „KFZ-KennzeichenM-AB1234" nie były w ogóle
  rozpoznawane, ponieważ leżące u podstaw sprawdzenie tablicy wymaga
  przed tablicą znaku niebędącego znakiem słowa. Dotyczyło to danych
  pojazdu, gdzie między słowem pola a tablicą nie ma spacji.
- Numer telefonu bez żadnej spacji do opisu pozostawał otwarty –
  „Handynummer0171/2345678" lub „Tel0171/2345678" nie były w ogóle
  rozpoznawane, ponieważ leżące u podstaw sprawdzenie numeru telefonu
  wymaga przed numerem spacji lub znaku interpunkcyjnego. Dotyczyło to
  danych kontaktowych, gdzie między słowem pola a numerem nie ma spacji.
- Nazwisko rodowe za skrótem „geb." nie było w ogóle rozpoznawane –
  „Julia Bergmann (geb. Weber)" znajdowało tylko „Julia Bergmann", kropka
  w „geb." sprawiała, że model językowy całkowicie pomijał następujące
  nazwisko. Dotyczyło to danych osobowych z nazwiskiem rodowym w nawiasie
  lub po przecinku.
- Imię przed pseudonimem w cudzysłowie pozostawało otwarte, gdy zwrot
  grzecznościowy i tytuł stały razem przed nim – „Herr Dr. Klaus "KP"
  Peters" dawało tylko „Peters", „Klaus" pozostawało czytelne. Dotyczyło
  to podpisów i danych kontaktowych z tytułem i pseudonimem.
- Nazwisko za bezkropkową skróconą formą „zH"/„zHd" (do rąk) nie było w
  ogóle rozpoznawane – w odróżnieniu od „z.Hd." z kropką, brakująca
  struktura zdania wciągała nazwisko razem ze sobą. Dotyczyło to adresów
  bez kropki w skrócie.
- Nazwisko za „p.A." (za adresem) nie było w ogóle rozpoznawane – kropka
  w skrócie sprawiała, że model językowy całkowicie pomijał rozpoznawanie
  nazwiska. Dotyczyło to faktur i podań ze wspólnym adresem.
- Nazwisko za bezkropkowo doklejonym „i.A."/„i.V." (w imieniu/w
  zastępstwie) nie było w ogóle rozpoznawane, np. „i.A.Robert Lang" bez
  spacji – ten sam błąd budowy zdania co przy „p.A.". Dotyczyło to
  wierszy podpisu i sygnatur mailowych w przypadkach zastępstwa.
- Czysta lista obecności w formie wypunktowania bez żadnych dalszych
  danych („- Max Mustermann", również z kropką na końcu wiersza) traciła
  wszystkie nazwiska na ten sam hamulec, który miał chronić właściwie
  tylko wyliczenia rzeczowe, takie jak „- Farbe: Blau". Takie listy są
  teraz rozpoznawane.
- Pliki, których nie dało się już oczyścić, dają się znów oczyszczać.
  Wartość, która była już zastąpiona przez rozpoznawanie, mogła zostać
  ponownie znaleziona we własnym, już zastąpionym znaczniku, takim jak
  „[SVNR1]" – kontrola końcowa odrzucała wtedy nienagannie oczyszczony
  plik. Ponadto odnośnik telefoniczny w tabeli CSV jest teraz również
  usuwany, a kto ogranicza wyszukiwanie do pojedynczych rodzajów, dostaje
  je teraz jednolicie w całym dokumencie – również w tekście
  alternatywnym obrazu, nagłówku Excel, liście wyboru lub atrybucie HTML.
- Nazwisko za nagłówkiem maila „To:" (lub „To" bez dwukropka) nie było
  rozpoznawane, ponieważ obcy model językowy odczytywał cały wiersz jako
  jedno niepozorne trafienie i całkowicie połykał w nim nazwisko – w
  odróżnieniu od „Cc:", „Bcc:" lub „From:" przed tym samym nazwiskiem.
  Nazwisko za „To" jest teraz niezawodnie znajdowane.
- Data ślubu nie dawała się we własnych regułach traktować jako data
  („przenieś" było odrzucane komunikatem „istnieje tylko dla dat"),
  brakowało jej w przyporządkowaniu grupowym rodzajów trafień – przez co
  nie dało się jej wyłączyć przez znaczniki „Co jest wyszukiwane" – i
  otrzymywała zamiast krótkiego skrótu, jak przy dacie zgonu, pełne
  brzmienie jako symbol zastępczy. Poprawiono dla wszystkich sześciu
  tabel skrótów/opisów.
- Wartość świadomie odznaczona w podglądzie mogła mimo to zostać
  zaczerniona w innym miejscu: kto np. odznaczył adres e-mail, adres sam
  pozostawał wprawdzie na miejscu, ale jego część lokalna bez domeny była
  zastępowana, gdy tylko pokrywała się z wyprowadzoną nazwą użytkownika
  dalej wybranej osoby („anna.musterfrau@beispiel.de" obok „Anna
  Musterfrau"). Odznaczone brzmienie pozostaje teraz tabu w całym
  dokumencie, niezależnie od tego, z jakiego rodzaju trafienia pochodzi.
- Data urodzenia pozostawała nierozpoznana, gdy wyciąg z księgi rodzinnej
  lub aktu stanu cywilnego prowadził ją pod wspólnym nagłówkiem z
  miejscem urodzenia („Geburtsdatum, Geburtsort: 19.11.1982, Steyr") –
  drugie słowo pola między „Geburtsdatum" a datą sprawiało, że
  rozpoznawanie do tej pory całkowicie zawodziło.
- Już rozpoznany numer telefonu pozostawał czytelny w swojej skróconej
  formie potwierdzającej, gdy w innym miejscu tego samego dokumentu był
  wymieniany tylko z ostatnimi czterema cyframi („erreichbar unter der
  Nummer ...5678", „Rückruf unter ...5678") – ta sama budowa co przy IBAN
  i karcie kredytowej.
- Już rozpoznany numer karty kredytowej pozostawał czytelny w swojej
  skróconej formie potwierdzającej, gdy w innym miejscu tego samego
  dokumentu był wymieniany tylko z ostatnimi czterema cyframi („Ihre
  Kreditkarte endet auf ...0366") – ta sama typowa w potwierdzeniach
  płatności budowa co przy IBAN.
- Już rozpoznany IBAN pozostawał czytelny w swojej skróconej formie
  potwierdzającej, gdy w innym miejscu tego samego dokumentu był
  wymieniany tylko z ostatnimi czterema cyframi („Die IBAN endet auf
  ...3201") – budowa typowa w mailach potwierdzających.
- Mówca w czacie lub protokole posiedzenia pozostawał nierozpoznany, gdy
  przed jego nazwiskiem stał zwrot grzecznościowy („Herr Bauer: …", „Frau
  Koch: …") – i przez to często dotykał również następnego wiersza
  mówcy w tym samym protokole, ponieważ zbyt mało rozpoznanych wierszy
  pozostawało, aby w ogóle uznać dokument za protokół.
- Data urodzenia pozostawała nierozpoznana, gdy słowo pola „geboren"
  stało ZA datą zamiast przed nią („Das Kind wurde am 14.01.2026
  geboren") – tak formułuje np. zaświadczenie o urlopie rodzicielskim lub
  ochronie macierzyństwa datę urodzenia dziecka. Dotychczasowe wzorce
  zakładały zawsze słowo pola przed datą.
- Opis formularza z reakcją emoji lub znacznikiem zaznaczenia bezpośrednio
  przed nim („Ansprechpartner 😊:", „Kontaktperson ✓:") nie był już
  rozpoznawany jako opis, a nazwisko pod nim lub za nim pozostawało przez
  to częściowo tylko niepełne znalezione (np. tylko nazwisko przy „Mayer
  Roman").
- Ta sama luka dotyczyła również szczególnie chronionych danych zgodnie z
  art. 9 RODO (religia, zdrowie, związek zawodowy): znak reakcji
  bezpośrednio przed separatorem lub złamaniem wiersza („Konfession 😊:
  römisch-katholisch") sprawiał, że opis całkowicie zawodził, a dane
  pozostawały całkowicie nierozpoznane.
- Adres z podwójną nazwą z łącznikiem w miejscowości (np. „79761
  Waldshut-Tiengen", „78050 Villingen-Schwenningen") tracił kod pocztowy
  w pełni, mimo że sama miejscowość była rozpoznawana i zaczerniana – na
  dokumencie pojazdu lub piśmie kod pocztowy pozostawał czytelny.
- Kolumna tabeli bez odstępu między kolumnami (prawdziwy wyciąg tekstu
  PDF) mogła pod kolumną nazwisk błędnie zaczernić również dwie
  przypadkowo stojące obok siebie wielkie litery jako osobę, np. dwie
  nazwy miejscowości w wierszu danych; jest to teraz tylko wtedy, gdy w
  tym samym miejscu żadne inne trafienie nie rozpoznaje już czegoś
  innego.
- Ta sama kolumna nazwisk zaczerniała w tej samej formie wiersza również
  dwa nieznane modelowi językowemu słowa rzeczowe (np. „Frontend
  Backend", „Turbo Modul") błędnie jako osobę, ponieważ tam żadne inne
  trafienie nie uruchamiało hamulca; wymaga teraz dodatkowo, aby
  przynajmniej jedno z obu słów było przez sam model językowy odczytane
  jako nazwa własna.
- Niemiecki numer ubezpieczenia rentowego w swoim urzędowym pełnym
  grupowaniu (np. „65 170839 J 08 8" – tak, jak stoi na legitymacji
  ubezpieczeniowej i odcinku wypłaty) nie był rozpoznawany i pozostawał w
  oryginale; rozpoznawana była tylko forma zwarta i forma grupowana tylko
  do litery.
- Numer identyfikacji podatkowej w swojej urzędowej pisowni (grupowanie
  2-3-3-3, np. „48 836 075 988" – tak, jak stoi na każdej prawdziwej
  decyzji podatkowej i każdym piśmie Federalnego Urzędu Centralnego ds.
  Podatków) nie był w ogóle rozpoznawany i pozostawał w oryginale; objęte
  było tylko rzadsze grupowanie 3-3-3-2.
- Numer podatkowy Nadrenii Północnej-Westfalii (np. „221/5147/0815", z
  czterocyfrową zamiast trzycyfrową drugą grupą) nie był rozpoznawany w
  decyzjach podatkowych i pozostawał w oryginale – każdy inny kraj
  związkowy był już objęty.
- W umowach o pracę nazwisko za opisem „Arbeitgeber:" (Pracodawca) było
  całkowicie pomijane, gdy tylko nazwisko było jednocześnie zwykłym
  słowem (np. „Bauer Anna") – „Arbeitgeber" stoi na liście zarówno jako
  opis nazwiska, jak i firmy, a przyporządkowanie firmy nadpisywało
  przyporządkowanie nazwiska.
- W nagłówku umowy najmu z opisami „Vermieter:"/„Mieter:"
  (Wynajmujący/Najemca) nazwisko, które było jednocześnie zwykłym słowem
  (np. „Bauer"), było pomijane – rozpoznawane pozostawało tylko imię.
  Numerowane strony najmu („Mieter 1:", „Mieter 2:") były dodatkowo
  dotknięte, również przy nazwiskach bez tej dwuznaczności.
- W protokole sądowym z opisami „Zeuge:"/„Kläger:"/„Beklagter:" (Świadek/
  Powód/Pozwany; również z numeracją, „Zeuge 1:", „Zeuge 2:") nazwisko,
  które było jednocześnie zwykłym słowem (np. „Bauer"), było podobnie
  pomijane – rozpoznawane pozostawało tylko imię.
- Przy poświadczeniu dziedziczenia, pełnomocnictwie, postępowaniu
  upominawczym i umowie kupna nazwisko, które było jednocześnie zwykłym
  słowem (np. „Bauer"), było pomijane za opisami, takimi jak
  „Erblasser:", „Erbe:", „Vollmachtgeber:", „Bevollmächtigte:r",
  „Antragsgegner:", „Schuldner:", „Gläubiger:", „Käufer:", „Verkäufer:",
  „Vermächtnisnehmer:" lub „Testamentsvollstrecker:" – częściowo
  rozpoznawane pozostawało tylko imię, częściowo całe nazwisko odpadało.
- Przy liście wielostronnej przed separatorem rubrum „./." (np. „Sand,
  Werner und Huber, Anna ./. Wechsler, Martina") pierwsza strona
  pozostawała niezamaskowana – rozpoznawana była tylko strona
  bezpośrednio graniczna z „./.".
- W separatorze rubrum „./." (np. „Sand./.Wechsler") nazwisko po znaku
  było całkowicie pomijane, gdy nie było tam spacji – rozpoznawanie
  trafiało tylko ze spacją przed i po.
- Nazwisko „Wahr" (Prawda) było całkowicie pomijane, gdy stało samodzielnie
  (np. „Frau Wahr bearbeitet Ihren Vorgang.") – słowo to stoi przypadkowo
  również na liście zwykłych niemieckich słów, która inaczej filtruje
  trafienia nazwisk ze zdań, takich jak „Das ist wahr.".
- Nazwiska, takie jak „Los", „Weit", „Rund" lub „Hoch", były całkowicie
  pomijane, gdy stały samodzielnie (np. „Herr Hoch übernahm die
  Leitung.") – wszystkie cztery słowa stoją przypadkowo również na liście
  zwykłych niemieckich słów, która inaczej filtruje trafienia nazwisk ze
  zdań, takich jak „Rund einhundert Gäste kamen zur Feier.".
- Nazwiska, takie jak „Ganz" lub „Recht", były całkowicie pomijane, gdy
  stały samodzielnie (np. „Herr Ganz unterschrieb den Vertrag.") – oba
  słowa stoją przypadkowo również na liście zwykłych niemieckich słów,
  która inaczej filtruje trafienia nazwisk ze zdań, takich jak „Ganz
  genau, das stimmt.".
- Pole formularza z gwiazdką lub górnym indeksem cyfry przypisu
  bezpośrednio za opisem (np. „Konfession*: römisch-katholisch" lub
  „Religionszugehörigkeit¹: evangelisch") nie było rozpoznawane i
  pozostawało w czystym tekście – trafiała tylko forma bez tego znaku.
- To samo pole pozostawało nadal w czystym tekście, gdy za opisem stały
  aż dwa znaki przypisu (np. „Konfession**: römisch-katholisch" lub
  „Gewerkschaft¹²: ver.di").
- Numer wersji, taki jak „Softwareversion 4.2.1.19" lub „Firmware Build
  2.0.4.11", nie jest już błędnie zaczerniany jako adres IP. To samo
  dotyczy teraz numerów dowodów i procesów, takich jak „Rechnungsnummer
  10.20.30.40" lub „Bestellnummer 7.8.9.10".
- Dwa numery IBAN bezpośrednio jeden pod drugim (np. własny i partnera
  zagranicznego w nagłówku faktury) nie były już rozpoznawane oba – drugi
  pozostawał niezauważony.
- Opisany IBAN czasami wciągał następujące słowo w zdaniu ("Bankverbindung
  AT61 … wird belastet" było zaczerniane aż do "wird"), gdy tylko
  następujące słowo było pisane małą literą – reszta czystego tekstu obok
  pozostawała przy tym nienaruszona.
- Adresy z Liechtensteinu są teraz rozpoznawane („FL-9490 Vaduz"), tak jak
  dotychczas już niemieckie, austriackie i szwajcarskie.
- Numer paszportu jest teraz rozpoznawany i usuwany za swoim opisem (np.
  „Reisepassnummer: C01X00T471").
- Numer tytułu pobytu i zaświadczenia o zameldowaniu jest teraz
  rozpoznawany i usuwany za swoim opisem.
- Numer identyfikacyjny za swoim opisem jest teraz rozpoznawany również,
  gdy zamiast dwukropka rozdziela myślnik (np. „Kundennummer – K903944").
- Połączenie bankowe opisane jako „IBAN" lub „Kontonummer" jest teraz
  rozpoznawane również, gdy zamiast dwukropka rozdziela myślnik.
- Nazwisko za opisem, takim jak „Kontaktperson (Vertrieb)" lub
  „Sachbearbeiter/in", jest teraz rozpoznawane również z dopiskiem w
  nawiasie lub neutralną płciowo końcówką z ukośnikiem.
- Ta sama forma z gwiazdką neutralna płciowo („Sachbearbeiter*in") jest
  teraz również rozpoznawana.
- Nazwisko za opisem jest teraz rozpoznawane również, gdy zamiast
  dwukropka rozdziela znak równości (np. „Ansprechpartner = Mayer Roman"
  lub „Kontaktperson=Mayer Roman"), jak to zwykle bywa w plikach
  konfiguracyjnych lub nagłówkach CSV. Jeśli w wierszu znajduje się kilka
  takich par opis-wartość rozdzielonych średnikiem, rozpoznawana jest
  teraz tylko pierwsza wartość zamiast całej reszty wiersza.
- Para współrzędnych GPS za słowem „Koordinaten" jest teraz niezawodnie
  rozpoznawana (np. „Koordinaten: 48.2082, 16.3738") – słowo miało
  niewłaściwą formę odmiany w wewnętrznym katalogu.
- Numer identyfikacyjny za swoim opisem (numer klienta, numer umowy,
  sygnatura akt, numer dowodu osobistego i około sto innych słów pól) nie
  był już rozpoznawany, gdy tylko opis nie stał dokładnie w zapisanej
  wielkości liter – „kundennummer:" w mailu lub „KUNDENNUMMER:" w
  nagłówku formularza pozostawały nienaruszone.

### Nowość

- **Realistyczne wartości zastępcze są teraz świadomie stosowanym
  przykładem, a nie ustawieniem domyślnym.** Tabela wyjątków w karcie
  „Symbole zastępcze" zaczyna się pusto. Nowy przycisk wpisuje na życzenie
  wiarygodne fałszywe wartości dla nazwiska, miejscowości, adresu,
  organizacji, e-maila, telefonu, numeru wewnętrznego i IBAN. Wyraźnie
  pozostawia kwoty pieniężne przy numerowanym symbolu zastępczym;
  strategia „wymyśl" pozostaje nadal wybieralna ręcznie dla poszczególnych
  rodzajów.
- **Poziom AI może wykorzystywać kartę graficzną.** Pod Windows można w
  tym celu doładować niewielki, prawie 17 MB pakiet dodatkowy; potem
  poziom AI liczy na odpowiedniej karcie graficznej wyraźnie szybciej niż
  na procesorze. Kto jej nie ma lub niczego nie doładuje, pracuje bez
  zmian dalej – tylko wolniej. Na macOS przyspieszenie jest i tak już
  wbudowane.
- **Dwa nowe powiadomienia przez ikonę paska zadań**: gdy podgląd jest
  gotowy do przejrzenia przed zastąpieniem i gdy przetwarzanie jest
  ukończone. Oba są domyślnie włączone i można je wyłączać osobno w
  *Ustawienia → Program → Powiadomienia*.

### Zmieniono

- **Numer dowodu osobistego i prawa jazdy są teraz rozpoznawane**, gdy
  stoi przed nimi ich opis („Personalausweisnummer: …", „Führerscheinnummer:
  …") – dotychczas oba przechodziły przez każde rozpoznawanie.
- **Maskuro podąża teraz za projektami kontrastu Windows.** Kto pod
  *Ustawienia → Ułatwienia dostępu → Motywy kontrastu* włączył jeden z
  nich, dostawał go dotychczas wszędzie oprócz tutaj – Maskuro ustawiało
  potem swoje własne kolory. Teraz pozostaje przy motywie systemu – okno,
  listy, strefa upuszczania, protokół i kolory statusu. Kolorowa
  sygnalizacja kontrolna w podglądzie i oknie poprawek celowo odpada tam –
  to, co mówi, i tak od dawna stoi obok jako znak i słowo.
- **Potrzeba kontroli nie jest już wyrażana tylko kolorem.** Czerwony,
  pomarańczowy i zielony są niemal jednakowo jasne – kto ma zaburzenie
  rozpoznawania czerwieni i zieleni, widział w podglądzie i panelu
  trafień listę bez różnic, a dotyczy to co dwunastego mężczyzny. Każdy
  wiersz niesie teraz dodatkowo znak, który różni się kształtem: ▲ sprawdź
  najpierw, ● sprawdź, ○ dobrze udokumentowane, ◆ bez oceny. Krótka
  wskazówka nazywa to słowami, a czytnik ekranu to odczytuje.
- **Alt znów otwiera menu jak zwykle.** Pasek menu nie miał skrótów
  klawiaturowych: kto nie używał myszy, musiał przechodzić przez każde
  menu strzałkami. Teraz każdy wpis niesie podkreśloną literę – Alt+P dla
  „Plik", stamtąd Z dla „Zakończ" – i to we wszystkich językach
  interfejsu.
- **Elementy obsługi znów mówią czytnikowi ekranu, do czego służą.** W
  oknie poprawek, oknie reguł, protokole, listach słów, pomocy, wyszukiwaniu
  i pięciu kolejnych oknach listy, pola wyszukiwania, listy rozwijane i
  suwaki były dotychczas ogłaszane tylko jako „drzewo" lub „pole
  kombi" – bez informacji, czego dotyczą. Około czterdzieści miejsc niesie
  teraz nazwę. (Okno główne było w porządku od sierpnia; okna, które doszły
  później, nigdy nie przeszły tego kroku.)
- **Kto obsługuje klawiaturą, widzi wszędzie, gdzie się znajduje.** Przy
  suwakach potrzeby kontroli, przy polu wyboru i przycisku „nigdy więcej"
  podglądu, przy nagłówkach rodzajów w nim, przy panelu stron okna
  poprawek i przy pasku bocznym ustawień brakowało ramki, którą system
  inaczej stawia wokół zaadresowanego elementu obsługi.
- **Większa czcionka systemowa niczego już nie ucina.** Kto pod
  *Ułatwienia dostępu → Rozmiar tekstu* ustawi powyżej 175%, tracił
  dotychczas koniec opisów w monitorowaniu folderów i polach skrótów
  klawiszowych. Lista rozdziałów pomocy ucinała długie nazwy rozdziałów
  już przy zwykłej czcionce; teraz je łamie i podaje pełną nazwę w
  krótkiej wskazówce.

- **Rozpoznawanie stało się wyraźnie szybsze.** Rozpoznawacz opisanych
  numerów identyfikacyjnych („Kundennummer: K903944") sprawdzał
  dotychczas na fragment tekstu ponad 1200 pojedynczych wzorców po
  kolei – to była największa pojedyncza pozycja czasu rozpoznawania, przy
  każdym akapicie i każdej komórce tabeli. Teraz jest to jeden wzorzec z
  tym samym wynikiem: w korpusie pomiarowym nie zmienia się ani jedno
  trafienie, poziom podstawowy na fragment tekstu jest około trzy- do
  czterokrotnie szybszy.
- **Okno pojawia się od razu przy starcie.** Dotychczas okno główne
  ładowało pełne narzędzia językowe, zanim w ogóle się pokazało – około
  cztery sekundy pustego czasu przy każdym starcie. Modele ładują się
  teraz zgodnie z zamierzeniem w tle, podczas gdy okno już stoi; przycisk
  Oczyść staje się jak dotychczas dostępny dopiero, gdy wszystko jest
  gotowe. Również czyste wywołania informacyjne wiersza poleceń (np.
  `--version`) odpowiadają teraz od razu zamiast po kilku sekundach.
- **Obrazy są przy automatycznym rozpoznawaniu języka odczytywane tylko
  raz.** Dotychczas rozpoznawanie tekstu przebiegało przy ustawieniu
  domyślnym „Język: automatycznie" dwukrotnie po tym samym obrazie – raz
  do przypuszczenia języka, raz do właściwego sprawdzenia. Pliki obrazów,
  obrazy ze schowka i okno tekstowe są przez to gotowe około dwa razy
  szybciej; przy wyłączonym rozpoznawaniu tekstu odpada całkowicie
  dotychczas niezauważenie i tak działający odczyt.
- **Zapisane strony internetowe i maile są oczyszczane szybciej.** Wartości
  w atrybutach HTML, komentarzach i osadzonych blokach danych były
  dotychczas rozpoznawane pojedynczo – strona gminy z setkami opisów
  stawiała setki pojedynczych zapytań do rozpoznawania. Teraz są zbierane
  i rozpoznawane tylko raz na różną wartość; w korpusie pomiarowym nie
  zmienia się żadne trafienie, .html i .eml są około jedną trzecią
  szybsze.
- **Również dodatkowe magazyny tabel i prezentacji są rozpoznawane
  zbiorczo.** Teksty alternatywne, ciągi znaków formuł, opisy wykresów,
  komentarze, pamięć podręczna tabel przestawnych i właściwości dokumentu
  stawiały na wartość osobne pytanie rozpoznawania – skoroszyt z
  tysiącami wierszy tabeli przestawnej odpowiednio tysiące. Teraz
  przebiega zbiorczy przebieg po różnych wartościach, a końcowy pełny
  przebieg dociągający działa już tylko wtedy, gdy od tekstu ciągłego
  faktycznie doszły nowe wartości. W korpusie pomiarowym nie zmienia się
  żadne trafienie.
- **Pliki PDF bogate w formularze są oczyszczane szybciej.** Pola,
  notatki, zakładki i odnośniki powtarzają te same wartości masowo
  („Off" przy każdym polu wyboru, ten sam autor przy każdej adnotacji) –
  każdy stawiał dotychczas własne pytanie rozpoznawania. Na przebieg
  wartość jest teraz rozpoznawana już tylko raz; zastąpienie i dopasowanie
  spójności przebiegają jak dotychczas na miejsce.
- **Duże pliki tabel (.csv/.tsv) są oczyszczane wyraźnie szybciej.** Cztery
  przebiegi dociągające tabel dzieliły dotychczas ten sam plik za każdym
  razem same, znak po znaku, na komórki (przy 40 MB około 30 s dodatkowej
  pracy); teraz podział przebiega raz. Rozpoznawanie nagłówka kolumny
  (kolumny dat urodzenia i numerów personalnych) stawia zamiast pytania
  na komórkę pytanie zbiorcze – przy identycznych trafieniach około
  dwadzieścia razy szybciej. A zestawienie kolumn nazwisk dużych list
  personalnych nie jest już kwadratowe względem liczby wierszy.
- **Klapka wskaźników nie zamraża już okna.** Rozwijanie wskaźników
  odczytywało przy wielu dużych plikach najpierw ich tekst i zatrzymywało
  przy tym okno na kilka sekund. Obliczenie działa teraz w tle; klapka
  otwiera się od razu i dociąga liczby.
- **Raport z wyszukiwania nie zamraża już okna.** Po przeszukaniu wielu
  tysięcy plików wspólny folder był obliczany na nowo dla każdego
  dotkniętego pliku; przy dużych przebiegach okno stało przy tym
  dwucyfrowo sekund. Raport pojawia się teraz od razu.
- **Pliki PDF z rozpoznawaniem tekstu są sprawdzane szybciej.** Każda
  strona była przy kontroli niepotrzebnie dwukrotnie przekształcana na
  format PNG; teraz przekazywany jest już istniejący obraz. Wynik jest
  niezmieniony, tylko sprawdzanie przebiega szybciej.
- **Adnotacje z gradientem na dużych obrazach już nie się zacinają.** Przy
  przeciąganiu uchwytów adnotacji z gradientem gradient był dotychczas
  obliczany na nowo punkt po punkcie – na dużym zrzucie ekranu widoczne
  zacinanie. Wynik jest ten sam, tylko bez przerwy.

### Naprawiono

- **Krzyżyk do usuwania pliku z listy jest znów zwykłym X.** Nowe
  narzędzie edytora „Usuń" przypadkowo używało tego samego identyfikatora
  symbolu i przez to pokazywało swój czerwony krzyżyk wraz z przerywaną
  linią tekstu również w każdym wierszu pliku. Obie czynności mają teraz
  osobne nazwy symboli i zachowują swoją odpowiednią prezentację.
- **Dane wieloczęściowe są w plikach PDF rozpoznawane również przez
  widoczne złamanie wiersza.** Maskuro odczytuje geometrycznie
  wygenerowany tekst strony dodatkowo jako widok tekstu ciągłego o tym
  samym przesunięciu. Dotyczy to wszystkich rozpoznawaczy podstawowych i
  wysokiego poziomu oraz własnych wzorców wyszukiwania, nie tylko
  pierwszego widocznego przypadku „Diabetes mellitus Typ 2". Puste
  wiersze i rozpoznane granice tabel lub sekcji pozostają twardymi
  granicami; miejsca trafień nadal pasują dokładnie do zaczernianych
  słów.
- **Przykład przy „Pseudonimizacja" zaprzeczał samemu sobie.** Zdanie
  obiecywało „ta sama osoba, ten sam numer", a potem pokazywało dwa różne
  numery – dokładnie ten obraz, który jest właściwy przy „Anonimizacja".
  Oba przykłady są teraz zgodne z własnym zdaniem.
- **Świeżo wstawiony symbol zastępczy mógł przy „Przywróć oryginał"
  pozostać jako nałożona na siebie masa liter zamiast zniknąć.**
  Jednokolorowo wstawiony symbol zastępczy pisał dotychczas własne
  polecenie wyjściowe na znak, z których tylko pierwszy niósł własną
  macierz tekstową – przy kolejnej edycji tego samego miejsca (np.
  „przywróć" bezpośrednio potem) pozostałe polecenia znaków otrzymywały
  kolejno indeksy znaków pierwszego, a symbol zastępczy rozpadał się na
  dwie nakładające się pozycje. Jednokolorowy symbol zastępczy otrzymuje
  teraz jedno jedyne polecenie wyjściowe dla całego swojego tekstu.

- **Jeśli ta sama zaczerniona lub usunięta wartość stała pod dwoma
  wierszami w oknie poprawek i oba zostały oznaczone do cofnięcia, drugi
  wiersz liczył się błędnie jako „niejednoznaczny" – mimo że wartość była
  już dawno przywrócona.** Oba wiersze liczą się teraz jako zakończone.

- **Nazwisko za „Reply-To:" jest teraz znajdowane.** W nagłówku maila,
  takim jak „Reply-To: Huber", nazwisko pozostawało dotychczas całkowicie
  nierozpoznane – model językowy odczytywał „Reply-To:" jako osobną,
  błędną osobę i pomijał prawdziwe nazwisko za nim.

- **Słowa nagłówka maila „Reply" i „Fwd" nie są już same zaczerniane jako
  nazwisko.** W wierszu tematu, takim jak „Fwd: Angebot von Huber",
  dotychczas oprócz nazwiska rozpoznawane i zaczerniane było również samo
  słowo nagłówka.

- **„Arbeitgeber: Siemens AG" jest teraz rozpoznawane jako firma, a nie
  jako osoba.** Jeśli wartość firmy za opisem „Arbeitgeber" niosła formę
  prawną, taką jak GmbH, AG lub KG, pozostawała mimo włączonego
  rozpoznawania organizacji trafieniem osobowym – rozpoznawany jako firma
  był dotychczas tylko węższy przypadek bez formy prawnej („Wollmuth und
  Partner").

- **Raz rozpoznany adres nie pozostaje już w innym miejscu.** Jeśli adres
  ulicy był rozpoznany i zastąpiony w jednym miejscu,
  ten sam adres mógł pozostać nierozpoznany w drugim miejscu – np. w
  trudno czytelnej stopce zeskanowanego dokumentu, gdzie automatyczne
  rozpoznawanie tekstu odczytywało go zniekształcony. Adresy są teraz,
  tak jak od dawna nazwiska i firmy, usuwane konsekwentnie w całym
  dokumencie.

- **E-maile z wieloma odbiorcami były przy oczyszczaniu po cichu
  uszkadzane.** Wiadomość `.msg` z dwoma lub więcej odbiorcami traciła
  przy zapisie części swojej wewnętrznej struktury, przez co oczyszczony
  wynik był niekompletny. Przyczyną było pomylenie identycznie nazwanych
  wewnętrznych elementów, które występują przy każdym odbiorcy. Takie
  wiadomości są teraz w pełni odbudowywane.

- **Dwa z dołączonych dokumentów testowych nie dawały się otworzyć w Word
  i PowerPoint.** Kto pobrał korpus pomiarowy, dostawał przy
  `format_dokument.docx` „Błąd podczas otwierania pliku w Word", a przy
  `format_praesentation.pptx` „Plik jest uszkodzony". Oba pliki były
  wadliwe jeszcze przed dotknięciem ich przez Maskuro – oczyszczona
  wersja niosła błąd tylko dalej. LibreOffice otwierało oba bez
  problemu, dlatego nikomu to nie wpadło w oko.

- **Własna AI w internecie jest teraz obsługiwana szyfrowanie.** Kto przy
  własnej AI wpisze zewnętrzny adres bez „https://" (jak często stoi na
  kartce od IT), docierał do niej dotychczas przez nieszyfrowane
  połączenie – niezaczerniony tekst wychodził w czystym tekście. Takie
  adresy są teraz obsługiwane przez „https://"; serwer we własnej sieci
  pozostaje bez zmian osiągalny. Jeśli serwer podąża za przekierowaniem
  na inny komputer, klucz dostępu już nie wędruje razem z nim.

- **Również uszkodzony obraz traci teraz swoje ukryte metadane.** Jeśli
  osadzonego obrazu nie dało się już w pełni otworzyć (np. ucięte
  zdjęcie), zachowywał dotychczas swoje dane EXIF i GPS – miejsce
  wykonania i nazwisko fotografa pozostawały niewidoczne w wyniku. Takie
  obrazy są teraz uwalniane od tych danych również wtedy, gdy nie dają
  się już w ogóle wyświetlić.

- **Osadzony plik, którego nie dało się oczyścić, jest teraz zgłaszany
  zamiast po cichu przekazywany dalej.** Jeśli w prezentacji lub
  skoroszycie leżał osadzony obiekt, który był zbyt głęboko zagnieżdżony
  lub nie dawał się otworzyć, pozostawał dotychczas bez zmian w wyniku,
  bez wskazówki – plik uchodził za oczyszczony. Takie przypadki stoją
  teraz w ostrzeżeniu „NIE udało się sprawdzić", dokładnie tak jak przy
  osadzonym starym formacie.

- **Ciemne listy są znów jednolicie ciemne i czytelne.** Na macOS listy
  plików zmieniały się między niemal czarnymi a jasnoszarymi wierszami;
  w oknie poprawek ta sama zielona, pomarańczowa lub czerwona wartość
  kontrolna wyglądała przez to inaczej w zależności od wiersza. Okno,
  listy, czcionka, symbole zastępcze i zaznaczenie pochodzą teraz ze
  wspólnej palety jasnej/ciemnej. Lista trafień z kodowaniem kolorami nie
  kładzie już ponadto pasków zebry pod swoimi kolorami.

- **Opisy zawodów z „als" (jako) były błędnie zaczerniane jako nazwisko.**
  Zdanie, takie jak „Als Koch ist er seit vier Jahren bei uns tätig.",
  traciło zawód, a nie tylko nazwisko – „als" wprowadza opis roli tak
  samo jak „der" czy „die". Prawdziwe nazwiska w tym samym miejscu (np. ze
  zwrotem grzecznościowym przed nimi) pozostają nienaruszone.

- **Nagłówek tabeli mógł wciągnąć numer pozycji w kwotę pieniężną** (tylko
  przy włączonej opcji „Usuń również kwoty pieniężne"). Jeśli wiersz
  kończył się walutą („… Einzelpreis EUR"), a następny zaczynał liczbą,
  powstawała z tego błędnie kwota przez złamanie wiersza. Separator
  między walutą a liczbą pozostaje teraz w tym samym wierszu.

- **Krótki skrót wielkimi literami mógł połknąć całą część zdania lub
  doczepić się przed poprawnie rozpoznane nazwisko.** Jeśli w wierszu
  stało dwuliterowe słowo wielkimi literami, takie jak „DI", „AG" lub
  „KG" – zwykłe skróty, nie nazwiska – cały wiersz był próbnie
  przeszukiwany małymi literami, a skrót wciągał przy tym czasami
  sąsiednie słowa (również czasowniki) w jedno rzekome nazwisko. Dopiero
  od trzech liter wielka litera uruchamia teraz to drugie sprawdzenie.
  Przy nieco dłuższych skrótach, takich jak „CEO" czy „USB", pozostawał
  drugi błąd: już poprawnie znalezione nazwisko („Schneider") otrzymywało
  poprzedzający skrót jako przedrostek dołączony do wyniku
  („CEO Schneider"). Skrót pozostaje teraz na zewnątrz.

- **Data urodzenia bez spacji za nią pozostawała nietknięta.** Jeśli za
  „geb." nie było odstępu przed datą – jak to zwykle bywa w ciasno
  ustawionych formularzach („geb.14.03.1988") – Maskuro nie rozpoznawało
  pola i pozostawiało datę nietkniętą. Rozpowszechnione skrócone formy,
  takie jak „Geburtsdat." lub „Geb.-Dat.", są teraz również rozpoznawane.

- **IBAN z ukośnikami jako separatorami pozostawał nietknięty.** Jak przy
  numerach telefonu („0664/1234567"), niektóre szablony piszą również
  IBAN w blokach z ukośnikiem („AT48/3200/0000/1234/5864") zamiast ze
  spacją lub łącznikiem. Ta pisownia jest teraz również rozpoznawana.

- **Austriacki numer ubezpieczenia społecznego z łącznikiem, kropką lub
  ukośnikiem pozostawał nietknięty lub był błędnie opisany.** Między
  dwoma blokami liczb przewidziana była dotychczas tylko spacja; pisownie,
  takie jak „1237-010180", „1237.010180" lub „1237/010180", nie były
  rozpoznawane (lub w przypadku ukośnika pod błędnym rodzajem). Cyfra
  kontrolna nadal potwierdza każde trafienie, niezależnie od separatora.

- **Nazwisko za „c/o" w adresie nie było w ogóle usuwane.** „c/o Max
  Mustermann, Hauptstraße 5, 1010 Wien" zaczerniało ulicę i miejscowość,
  ale pozostawiało nazwisko za tym w pełni na miejscu. Nazwisko jest
  teraz rozpoznawane; samo „c/o" pozostaje widoczne jako wskazówka
  adresowa.

- **Numer karty kredytowej pogrupowany kropkami pozostawał nietknięty.**
  Pisownie, takie jak „4111.1111.1111.1111", nie były rozpoznawane;
  numery rozdzielone spacją lub łącznikiem nie były tym dotknięte. Suma
  kontrolna nadal potwierdza każde trafienie.

- **Numer identyfikacji podatkowej pogrupowany łącznikami pozostawał
  nietknięty, austriacki numer VAT z łącznikiem lub kropką również.**
  Spacja, ukośnik i kropka były przy numerze identyfikacji podatkowej już
  przewidziane, brakowało łącznika; przy numerze VAT („ATU12345678")
  brakowało łącznika i kropki po prefiksie. Cyfra kontrolna numeru
  identyfikacji podatkowej nadal potwierdza każde trafienie.

- **Wartość pola w cudzysłowie pozostawała nietknięta, np. w wierszu w
  stylu JSON, takim jak „vorname": „Max".** Rozpoznawanie przez opis
  pola („Vorname: …") zakładało dotychczas, że ani opis, ani sama
  wartość nie stoją w cudzysłowie. Takie wiersze są teraz również
  rozpoznawane – tak samo jak opisy pól z poprzedzającym punktem listy
  YAML („- Vorname: Max") lub tabulatorem zamiast spacji przed
  dwukropkiem.

- **Słowo nagłówka maila „Sent" było samo zaczerniane jak nazwisko.** W
  nagłówku, takim jak „Sent: Huber", trafiało dotychczas zarówno „Sent",
  jak i właściwe nazwisko; pokrewne słowa nagłówka, takie jak „Subject"
  czy „Betreff", były od zawsze tym nienaruszone. „Sent" pozostaje teraz
  również na miejscu.

- Nazwisko za nagłówkami „Errors-To:" lub „Resent-From:" pozostawało
  niewykryte, gdy taki wiersz stał skopiowany w czystym tekście (np.
  przekazana wiadomość lub raport o incydencie) – w odróżnieniu od
  „Reply-To:" lub „Return-Path:" nazwisko odpadało tu całkowicie, zamiast
  być tylko nieprecyzyjnie odgraniczone. Jest teraz znajdowane.
- Ten sam plik dawał przy dwóch oczyszczeniach czasem różny wynik: gdy
  dwa rozpoznania trafiały dokładnie w to samo miejsce o tej samej
  długości i tej samej pewności (np. „Sozialversicherungsnummer
  1237/010180" jako AT_SVNR lub jako ogólny numer identyfikacyjny), było
  kwestią przypadku, które wygrywało – wartość była usuwana w obu
  przypadkach, zmieniał się tylko opis symbolu zastępczego. Remis jest
  teraz zawsze rozstrzygany tak samo.
- Oznaczenie funkcji bezpośrednio przed rzeczownikiem (np. „Behandelnder
  Arzt: Dr. …" lub „Zuständiger Sachbearbeiter ist …") było czasem
  błędnie razem zaczerniane, jakby samo było nazwiskiem. Prawdziwe
  nazwiska obok pozostają tym nienaruszone.
- Prawdziwe nazwisko, które przypadkowo wygląda jak przymiotnik (np.
  „Schöne", „Lange", „Junge") i stoi bezpośrednio przed kolejnym
  rzeczownikiem (np. „Kontaktperson: Schöne Assistentin"), pozostawało od
  ostatniej naprawy niezaczernione w tekście – wyciek danych. Tylko
  wąsko ograniczona lista prawdziwych oznaczeń funkcji (np.
  „Behandelnder", „Zuständiger") jest teraz traktowana w tej formie jako
  nie-nazwisko.
- Samodzielne nazwisko na końcu wieloliniowego trafienia nazwiska, które
  przypadkowo wygląda jak przymiotnik (np. „Schwarz", „Kurz", „Alt",
  „Frisch", „Gut", „Reich"), pozostawało przed bezpośrednio następującym
  dwukropkiem nierozpoznane – oczyszczanie myliło je z opisem pola,
  takim jak „Telefon:". Zamknięta lista znanych wieloznacznych nazwisk
  chroni je teraz.
- Samodzielne nazwisko, które przypadkowo jest zwykłym niemieckim słowem
  („Gross"/„Grosse", „Gut", „Kurz", „Lang"/„Lange"), było dotychczas
  **całkowicie** tracone – nawet w prostych zdaniach, takich jak „Herr
  Gross unterschrieb den Vertrag.". Przyczyną była własna lista stopwords
  spaCy, która zawiera te słowa; zamknięta lista znanych nazwisk chroni
  je teraz przed odrzuceniem.
- Przy umowach pracy, pożyczki, poręczenia, powiernictwa i upadłości oraz
  opiece prawnej/kurateli i zleceniach ekspertyz nazwisko, które było
  jednocześnie zwykłym słowem (np. „Bauer"), było pomijane za opisami,
  takimi jak „Auftraggeber:", „Auftragnehmer:", „Arbeitnehmer:",
  „Versicherter:", „Darlehensgeber:", „Darlehensnehmer:", „Bürge:",
  „Sicherungsgeber:", „Treuhänder:", „Treugeber:", „Insolvenzverwalter:",
  „Gutachter:", „Sachverständiger:", „Vormund:" lub „Pfleger:" – częściowo
  rozpoznawane pozostawało tylko imię, częściowo całe nazwisko odpadało.
- W stopce redakcyjnej nazwisko, które było jednocześnie zwykłym słowem
  (np. „Bauer"), było pomijane za opisami „Geschäftsführer:",
  „Geschäftsführerin:", „Vertretungsberechtigt:", „Inhaber:" lub
  „Inhaberin:" – przy „Geschäftsführer:"/„Inhaber:" odpadało całe
  nazwisko, przy „Vertretungsberechtigt:" rozpoznawane pozostawało tylko
  imię.
- Blok kontaktowy, którego opis stał samodzielnie w swoim wierszu i niósł
  neutralną płciowo formę z dwukropkiem („Ansprechpartner:in", nazwisko
  pod spodem), był **całkowicie** pomijany – dwukropek był odczytywany
  jako separator pola, „in" jako (odrzucona) wartość pola, a właściwe
  nazwisko w następnym wierszu nigdy więcej nie dochodziło do głosu.
  Forma z gwiazdką („Ansprechpartner*in") nie była tym dotknięta.
- Jeśli nazwisko i opis stały z tą samą formą płciową z dwukropkiem w
  **jednym** wierszu („Ansprechpartner:in Anna Berger"), symbol zastępczy
  wciągał słowo „in" w zastąpienie, zamiast usuwać tylko nazwisko – samo
  nazwisko było nadal w pełni wykrywane.
- Nazwisko w kolumnie tabeli pod nagłówkiem kolumny osobowej (np. „Name
  Vorname Geburtsdatum" nad „Bauer Anna 03.05.1985", jak w odcinku
  wypłaty) było całkowicie pomijane, gdy tylko między kolumnami stała
  pojedyncza spacja i żaden wiersz nie zaczynał się numerem gliederunku –
  dokładnie tak, jak prawdziwy wyciąg tekstu PDF dostarcza takie wiersze.
- W czacie lub protokole posiedzenia z nazwiskami mówców przed dwukropkiem
  (np. „Bauer 🙂: Ich stimme dem Vorschlag zu.") nazwisko pozostawało
  całkowicie nierozpoznane, gdy tylko między nazwiskiem a dwukropkiem
  stał znak reakcji, a nazwisko było jednocześnie zwykłym słowem
  („Bauer", „Koch", „Schneider" itp.) – cały protokół mógł przez to
  pozostać bez ani jednego rozpoznanego mówcy.
- Ta sama luka wierszy mówcy istniała również z innymi znakami pośrednimi
  przed dwukropkiem: dopiskiem statusu w nawiasie („Bauer (Vorsitz): …",
  „Bauer (abwesend): …"), godziną w nawiasach kwadratowych („Bauer
  [14:32]: …") i znakiem przypisu bezpośrednio przy nazwisku
  („Bauer*: …"). Również tu mówca pozostawał całkowicie nierozpoznany,
  gdy nazwisko było jednocześnie zwykłym słowem.
- Jeśli już rozpoznana osoba w dołączonym fragmencie protokołu lub logu
  tej samej wiadomości (np. ticket wsparcia) występowała dodatkowo jako
  nazwa użytkownika w formie „imię.nazwisko" – małą literą, bez spacji,
  połączona kropką –, ten czysty tekst pozostawał czytelny, mimo że to
  samo nazwisko w piśmie przewodnim było już zaczernione.
- Ta sama luka nazwy użytkownika istniała również z podkreśleniem zamiast
  kropki („imię_nazwisko") – równie rozpowszechniony format we
  fragmentach protokołów i logów.
- Nazwa użytkownika pozostawała czytelna również w odwrotnej kolejności
  („nazwisko.imię" lub „nazwisko_imię") – niektóre systemy stawiają
  nazwisko na początku nazwy użytkownika w logu zamiast na końcu.
- Data zgonu pozostawała nierozpoznana, gdy obok nie stały żadne inne
  dane („Herr Bauer ist am 12.03.1985 verstorben") – nie było na to
  dotychczas żadnego własnego rozpoznawania, a ogólna data nie trafia
  przy tym standardowym progu.
- Data zgonu pozostawała nierozpoznana również wtedy, gdy zdanie
  używało formy czasownikowej zamiast imiesłowu („Frau Meier verstarb am
  12.03.1985", „Er starb am 12.03.1985") – trafiało dotychczas tylko
  „ist … verstorben"/„ist … gestorben".
- Data ślubu pozostawała nierozpoznana, niezależnie od formy, w jakiej
  stała („Eheschließung am 12.03.2010", „Hochzeitsdatum: 12.03.2010",
  „Herr und Frau Bauer heirateten am 12.03.2010") – nie było na to
  dotychczas żadnego własnego rozpoznawania, a ogólna data nie trafia
  przy tym standardowym progu.

- **W edytorze poprawek druga ramka nad świeżo wstawionym symbolem
  zastępczym mogła pozostawić czerwoną resztkę znaków**, np. „[G" zamiast
  „[BEG1]" – bez żadnego ostrzeżenia, ponieważ resztka nie należała już do
  poufnych danych (te były usunięte już w pierwszym kroku), lecz tylko do
  własnego symbolu zastępczego. Przyczyną było kolorowanie: nowo
  wstawiony symbol zastępczy był zapisywany znak po znaku do pliku,
  nawet przy jednokolorowym ustawieniu domyślnym – kolejna ramka nad tym
  samym miejscem nie znajdowała przez to już żadnego spójnego brzmienia,
  do którego mogłaby się odnieść. Teraz jednokolorowy symbol zastępczy
  stoi jako jeden kawałek w strumieniu, tak jak od zawsze robiło to
  automatyczne oczyszczanie; tylko prawdziwy tekst z gradientem lub tęczą
  nadal potrzebuje pojedynczych znaków. Wbudowana kontrola porównawcza
  rozpoznaje taką resztkę teraz dodatkowo również wtedy, gdy dokładny
  ciąg znaków symbolu zastępczego już nie występuje.
- Numerowana lista nazwisk ze stopniowanym numerem gliederunku
  („1.1 Max Mustermann", „1.2 Huber Franz" …) traciła wszystkie nazwiska
  na ten sam hamulec, który miał chronić właściwie tylko prawdziwe
  gliederungi i listy pozycji – bez nagłówka kolumny nad listą nie było
  świadka, dzięki któremu nazwisko mogłoby się uratować.
- Nazwisko w angielskojęzycznym wierszu logowania protokołu systemowego
  („Accepted password for Max Mustermann from 10.0.0.5 port 51000 ssh2")
  nie było rozpoznawane – niemiecki model językowy znajdował je tylko,
  gdy przed nim stało „invalid user", w przeciwnym razie pozostawało na
  miejscu. Takie fragmenty protokołów są często dołączane bez zmian do
  raportu o incydencie. Nazwiska za „for" przed adresem IP są teraz
  niezawodnie rozpoznawane.
- Nazwisko płatnika w referencji mandatu SEPA wyciągu z konta lub dziennika
  księgowań (np. „MREF+Mustermann Klaus+SVWZ+Miete August") pozostawało
  otwarte – żadnej spacji, żadnej struktury zdania, tylko pola wielkimi
  literami rozdzielone „+", a w tam typowej kolejności „Nazwisko Imię"
  rozpoznawanie nie trafiało go też przypadkowo. Jest teraz rozpoznawane.
- Ulica wraz z numerem domu w pierwszym wierszu tabeli adresowej (np.
  „Nazwisko | Imię | Ulica | Kod pocztowy | Miejscowość") pozostawała
  otwarta – model językowy zgadywał tam błędne, ale dłuższe miejsce
  ponad kilkoma kolumnami, które wypierało prawidłowe, krótsze trafienie
  adresu. Jest teraz rozpoznawana.
- Ten sam wyciek występował z tabulatorem zamiast „|" lub „;" jako
  separatorem kolumn – tam adres znikał nawet całkowicie zamiast tylko
  częściowo. Jest teraz rozpoznawany.
- Ulica z numerem domu pozostawała otwarta, gdy bezpośrednio po niej bez
  spacji następował kod pocztowy z przecinkiem (np. „Bahnhofstrasse
  12,80331 München", jak w kolumnie tabeli rozdzielonej przecinkami) –
  przecinek wyglądał jak miejsce po przecinku dziesiętnym ilości, i ulica
  w ogóle nie liczyła się wzorcowi jako adres. Jest teraz rozpoznawana.
- Ulica z numerem domu pozostawała otwarta, gdy bezpośrednio po niej bez
  przecinka następował przedrostek miejscowości „St." (Sankt) (np.
  „Hauptstraße 5 St. Pölten", nagłówek listu bez poprzedzającego kodu
  pocztowego) – „St." wyglądało jak jednostka sztuk, i ulica w ogóle nie
  liczyła się wzorcowi jako adres. Jest teraz rozpoznawana.
- Dopisek drzwi/klatki schodowej po numerze domu (np. „Lerchenfelder
  Gürtel 43/12") pozostawał otwarcie widoczny, gdy bezpośrednio po nim
  stała pojedyncza litera, która przypadkowo zgadza się z jednostką miary
  (np. „h" dla godziny) – adres był wtedy oczyszczany tylko do numeru
  domu bez jego dopisku, zamiast trafiać w pełni albo wcale.
- Wiersz tematu z nazwiskiem zgodnym z nazwą zawodu przed imieniem
  („Betreff: Bauer Anna", „Betreff: Bauer, Anna") pozostawał dotychczas
  całkowicie nierozpoznany – nawet w środku dokumentu z poprzedzającym
  pełnym zdaniem. Jest teraz rozpoznawany.
- Niemiecki numer podatkowy ze spacją, kropką lub łącznikiem między
  blokami (np. „Steuernummer: 30 815 08153" lub „30.815.08153") pozostawał
  dotychczas nierozpoznany – znajdowana była tylko pisownia z ukośnikiem.
  Jest teraz rozpoznawany.
- Nazwisko za medycznym opisem pola („Patient:", „Hausarzt:", „Behandelnder
  Arzt:", „Überweisender Arzt:" i ich formy żeńskie) pozostawało
  dotychczas nierozpoznane, gdy nazwisko było jednocześnie zwykłym
  niemieckim słowem (np. „Patient: Bauer Thomas"). Jest teraz
  rozpoznawane.
- Nazwisko za opisem pola „Zahnarzt" (Dentysta) w osobnym wierszu (np.
  „Zahnarzt", pod spodem „Huber Franz") pozostawało dotychczas
  nierozpoznane – ani imię, ani nazwisko. „Zahnärztin" i prosta forma
  „Arzt" nie były tym dotknięte. Jest teraz rozpoznawane.
- Nazwisko za „Herr"/„Frau", po którym następowała urzędowa formułka,
  taka jak „zur Kenntnisnahme", „zur Unterschrift" lub „zur
  Weiterleitung", było dotychczas ujmowane zbyt szeroko i wciągało
  formułkę w trafienie nazwiska – z „Frau Petra Klein zur Vertretung in
  allen Angelegenheiten" zastępowane było „Petra Klein zur Vertretung", a
  reszta zdania pozostawała gramatycznie okaleczona. Prawdziwe predykaty
  szlacheckie, takie jak „von der Leyen" lub „zu Guttenberg", pozostają
  tym nienaruszone.
- Ta sama nadmierna redakcja urzędowej formułki dotyczyła również
  nazwiska w nagłówku maila „To:", kodzie dopuszczenia (C.1/C.1.1/C.1.2),
  kodzie prawa jazdy, oklamrowanym polu formularza („[Vorname]: …") i
  niepunktowanej formule powitalnej – wszędzie tam „zur"/„von" i inne
  wciągały następującą formułkę, taką jak „zur Unterschrift" lub „zur
  Vertretung", w trafienie, częściowo nawet samo słowo partykuły
  pozostawało w wyniku jako resztka nazwiska. Również tu prawdziwe
  predykaty szlacheckie pozostają w pełni zachowane.
- Numer indeksu za swoim opisem nie był dotychczas w ogóle rozpoznawany –
  „Matrikelnummer 7654321" przechodziło całkowicie przez rozpoznawanie,
  ani jako numer identyfikacyjny, ani przez model językowy, ponieważ sama
  liczba nie niesie rozpoznawalnej formy.
- To samo dotyczyło numeru uczestnika – „Teilnehmernummer 4471829"
  przechodziło całkowicie, ani jako numer identyfikacyjny, ani przez
  model językowy.
- W CV nazwisko pod nagłówkiem sekcji „Persönliche Daten" (Dane osobowe)
  często całkowicie lub częściowo przechodziło przez rozpoznawanie, gdy
  stało bez zwrotu grzecznościowego w formie „Nazwisko Imię" bezpośrednio
  pod spodem.
- To samo dotyczyło nagłówka sekcji „Kontaktdaten" (Dane kontaktowe) –
  tam nazwisko przechodziło nawet całkowicie, nie tylko częściowo.
- W zaświadczeniu o zameldowaniu lub liście wniosków ze złączoną kolumną
  „Name, Vorname" (pisownia meldunkowa, wartość np. „Mustermann, Max" w
  komórce) nazwisko przechodziło całkowicie przez rozpoznawanie, gdy
  następowała kolejna kolumna, taka jak data urodzenia.
- Data urodzenia w formie zwykłej na dowodzie osobistym i zaświadczeniu o
  zameldowaniu „Geburtsdatum/-ort: 22.07.1978 / Rostock" nie była
  rozpoznawana – trafiała tylko forma z przecinkiem „Geburtsdatum,
  Geburtsort: …".
- „Bürgerservice" i „Bürgerbüro" (Biuro obsługi obywatela) były czasem
  błędnie zaczerniane jako miejsce, zwłaszcza po myślniku jako
  separatorze wyliczenia (np. „Wenden Sie sich an das Bürgerservice –
  Bürgerbüro …").
- Opisany numer telefonu, który złamanie wiersza przecinało w środku
  (np. z wąskiej kolumny nagłówka listu lub ekstrakcji tekstu PDF na
  szerokość kolumny: „Telefon: 0176 12\n34567"), był częściowo zaczerniany
  tylko do połowy – reszta za złamaniem wiersza pozostawała czytelna.
- Opisany numer identyfikacyjny (klienta, członkostwa, umowy i podobne),
  który złamanie wiersza przecinało w środku (np. „Kundennummer:
  K903\n944" z wąskiej kolumny), był zaczerniany tylko do połowy – reszta
  za złamaniem wiersza pozostawała czytelna.
- Nazwisko z tytułem akademickim przed oznaczeniem zawodu po przecinku
  (np. „Dipl.-Ing. Sabine Roth, Projektleiterin") pozostawało w pełni bez
  ochrony – wiersz wyglądał jak tabelaryczny nagłówek kolumny i był
  błędnie odrzucany jako treść rzeczowa.
- Tytuł „Dr.-Ing." (częsty niemiecki stopień inżynierski) przed nazwiskiem
  nie był ujmowany w maskowaną wartość osobową i pozostawał czytelny –
  ta sama pułapka z łącznikiem co przy „Dipl.-Ing.".
- Tytuły „Dipl.-Kfm.", „Dipl.-Kffr." i „Dipl.-Psych." (dyplomowany
  kupiec/kupcowa/psycholog) przed nazwiskiem nie były ujmowane w
  maskowaną wartość osobową i pozostawały czytelne – ta sama pułapka z
  łącznikiem co przy „Dipl.-Ing." i „Dr.-Ing.".
- Adres MAC w pisowni Cisco z kropkami zamiast dwukropków (np.
  „aabb.ccdd.eeff", jak wypisują protokoły przełączników i zgłoszenia
  wsparcia) nie był w ogóle rozpoznawany i pozostawał czytelny.
- Nazwisko za „Familie" (Rodzina; np. „Die Familie Gruber unterschreibt
  den Vertrag") pozostawało w zależności od budowy zdania nierozpoznane i
  tym samym czytelne – również z predykatem szlacheckim przed nim
  („Familie von der Leyen").

- Przy chorwackim adresie bez znaku interpunkcyjnego oddzielającego
  między kodem pocztowym+miejscowością a ulicą+numerem domu (np. „10000
  Zagreb Ulica Ivana Lučića 5") numer domu pozostawał nieoczyszczony.

- Przy litewskim wpisie kontaktowym z opisem „Kontaktinis asmuo" (np.
  „Kontaktinis asmuo: Vilkas Jonas") nazwisko pozostawało nierozpoznane,
  gdy było jednocześnie powszechnym rzeczownikiem (Vilkas = „Wilk",
  Vanagas = „Jastrząb").

- Kraj urodzenia lub zamieszkania bez dalszego opisu w duńskim polu
  formularza (np. „Fødeland: Tyskland" lub „Bopæl: Tyskland") nie był
  rozpoznawany.

- Kraj urodzenia lub zamieszkania bez dalszego opisu w rumuńskim polu
  formularza (np. „Țara: Germania" lub „Țara de reședință: Franța") nie
  był rozpoznawany.

- Nazwa firmy pod litewskim opisem pola „Darbdavys:" lub „Įmonės
  pavadinimas:" (pracodawca/firma) nie była rozpoznawana.

- Nazwa firmy pod rosyjskim opisem pola „Работодатель:" lub „Наименование
  организации:" (pracodawca/firma) nie była rozpoznawana.

- Data wypisana słownie z nazwą miesiąca po rumuńsku (np. „31 decembrie
  2024") nie była rozpoznawana.

- Węgierskie nazwisko rodowe za skrótem „szül." (np. „Nagy Éva (szül.
  Kovács)") nie było rozpoznawane i pozostawało otwarcie czytelne.

- Zapisana strona profilowa HTML (lub mail z załączoną stroną
  internetową) mogła pozostawić nieoczyszczone imię i nazwisko cywilne,
  gdy stało tylko w polach profilowych Open Graph
  `profile:first_name`/`profile:last_name`/`profile:username` – te niosą
  imię i nazwisko rozłożone zamiast opisowo jak `og:title` i są teraz
  również oczyszczane.

- Powiadomienie o niedostarczeniu (Bounce/NDR) niosło często nagłówki
  pierwotnie niedostarczonego maila (nadawca, odbiorca, temat) w
  osobnej, trzeciej części załącznika – ta pozostawała w oczyszczonej
  wersji w pełni nietknięta. Ta część jest teraz oczyszczana tak samo jak
  pozostały raport o dostarczeniu.

- Indywidualnie nazwany redaktor obszaru chronionego w Word (Ogranicz
  edytowanie → Wyjątki, `w:permStart`) pozostawał w czystym tekście,
  nawet gdy to samo nazwisko w tekście ciągłym było już dawno oczyszczone.
  Jest teraz również usuwane.

## 0.10.42-alpha.20260827 – 27 sierpnia 2026

### Nowe

- **Nazwane profile rozpoznawania czynią różne przypadki robocze
  osiągalnymi jednym ruchem.** Pod *Ustawienia → Rozpoznawanie → Co jest
  usuwane* można zapisać bieżący wybór kategorii i rodzajów i przez pole
  wyboru zastosować go od razu ponownie. Stały profil *Standardowy*
  odpowiada dotychczasowemu stanowi wydania i nie da się go usunąć.
  Profil zmienia wyłącznie to, co jest usuwane; język, rodzaj wyjścia,
  głębokość rozpoznawania oraz własne pojęcia i wzorce wyszukiwania
  pozostają nienaruszone.

- **Rodzaj wyniku jest teraz wybierany bezpośrednio przed
  oczyszczeniem.** Wspólne pole wyboru w oknie głównym ustala dla całego
  pakietu, czy Maskuro wstawia czytelne zastępniki, zaciemnia czy usuwa
  bez zastępowania. Dwa osobne pola dla PDF i Office w oknie ustawień
  odpadły; przez to ważna decyzja jest widoczna i nie może się już przy
  mieszanych pakietach niezamierzenie rozjechać. Prowadzony Rundgang
  wyjaśnia nowy wybór przed pierwszym oczyszczeniem.

- **Motywy i znaki wodne wyraźnie oznaczają gotowe pliki PDF na
  życzenie.** Dwanaście ogólnych wyglądów dostraja teksty zastępcze i
  powierzchnie zaciemnienia do siebie; nowe są Pride oraz wiosna, lato,
  jesień i zima. *Tajne akta* wnosi od razu ukośny napis `TOP SECRET`.
  Niezależnie od tego można wybrać wolny tekst oznaczenia lub własny
  obraz, ikonę lub SVG z kolorem i krycia. Zaimportowana grafika jest
  osadzana bez swoich metadanych i pozostaje dostępna, gdy plik źródłowy
  zostanie przeniesiony. Przy poprawianiu Maskuro zastępuje swój
  dotychczasowy znak wodny, zamiast nakładać go wielokrotnie. Znaki
  wodne tekstowe są rysowane jako ostatnia warstwa PDF z jasnym konturem,
  żeby pozostawały widoczne także na ciemnych obrazach i gęstym tekście.
  Edytor poprawek całkowicie ignoruje znak wodny Maskuro i nie oferuje
  już jego tekstu jako kandydata do zaciemnienia.

- **Własne motywy wyjściowe można zapisywać i udostępniać.** Bieżąca
  mieszanka tekstu zastępczego, zaciemnienia i znaku wodnego otrzymuje
  nazwę, pozostaje w ustawieniach i można ją eksportować lub importować
  jako JSON bez jawnego tekstu. Podgląd druku czarno-białego ostrzega
  przed słabymi kontrastami; opcjonalne konfetti sukcesu pozostaje
  wyłącznie w interfejsie.

- **Ostatnia próba eksportu i wyjaśniająca warstwa sprawdzająca
  zamykają rundę przedstawienia.** Przed ostatecznym zapisem Maskuro
  porównuje jeszcze raz każde dokładnie znane co do wartości miejsce PDF
  w warstwie tekstu i wyrenderowanych pikselach; ostrzeżenia podają
  wyłącznie stronę i współrzędne. W edytorze *Dlaczego to jest zakryte?*
  pokazuje kategorię, drogę rozpoznania i margines bezpieczeństwa, nigdy
  usuniętego jawnego tekstu i nigdy w dokumencie końcowym.

- **Pasy zaciemniające mogą być teraz ładne.** Pod *Ustawienia → Wygląd*
  dostępne są wartości domyślne koloru, dowolne wybieraki kolorów,
  gradienty, tęcza, paski, kropki, kwiaty, gwiazdy, serca, łapki,
  chmury, błyskawice, ziarna kawy, kaczki, słońca, liście, płatki
  śniegu, wzory papieru, zakreślacza, taśmy klejącej i reprodukowalne
  wzory losowe wraz z natychmiastowym podglądem. Teksty zastępcze
  dostają opcjonalnie kolor, gradient, tęczę, pigułkę lub etykietę.
  Kolory kategorii rozróżniają nazwiska, adresy, kontakty i dane
  medyczne. PDF przejmuje pełne kształtowanie; Word, PowerPoint,
  OpenDocument i HTML używają wybranego kryjącego koloru podstawowego.
  Ochrona się przy tym nie zmienia: Maskuro usuwa poufną treść najpierw
  i dopiero potem rysuje kolor lub wzór na puste miejsce.

- **Maskuro jest znów dostępny dla Linuksa – jako AppImage, DEB, RPM i
  archiwum przenośne.** DEB i RPM wpisują do systemu wpis programu,
  przypisania plików, polecenie terminala i ikonę; AppImage działa bez
  instalacji. Aktualizacje pozostają przy istniejącej instalacji DEB lub
  RPM w tym samym formacie pakietu i poza tym preferują AppImage.

- **Kontrola wzrokowa nie przedkłada już zwykłego tekstu PDF po raz
  drugi jako nowych trafień.** Końcowe spojrzenie OCR i bezpieczna
  przebudowa widocznych stron pozostają w pełni aktywne; jako nowe
  źródło znalezienia liczą się jednak w ustawieniu domyślnym tylko
  obszary, których tekst strony i sprawdzenie pojedynczego obrazu jeszcze
  nie odczytały. Dzięki temu wiersze produktów nie stają się nowymi
  nazwiskami lub firmami tylko z powodu odbiegającego drugiego odczytu
  OCR. Kto nadal chce dwóch niezależnych osądów o całym widocznym
  tekście, włącza w ustawieniach *Sprawdź jeszcze raz całą widoczną
  stronę PDF pod kątem danych*.

- **Pliki PDF można oglądać ciągle, kartka po kartce lub jako podwójna
  strona.** Trzy kompaktowe ikony widoku siedzą na dole bezpośrednio
  obok „Szerokość” i „Strona”. Ciągły przewija na brzegu kartki do
  następnej strony; pojedyncza strona trzyma kółko myszy na bieżącej
  kartce; podwójna strona pokazuje arkusz, czyni kliknięty arkusz
  edytowalnym i przesuwa Naprzód/Wstecz o cały arkusz. Miniatury stron i
  lupa porównawcza otwierają się ponadto w wyraźnie węższej lewej
  kolumnie podstawowej i zostawiają stronie roboczej więcej miejsca.

- **Widzą Państwo teraz, co zrobił poziom SI.** Po każdym przebiegu pod
  „Szczegóły” stoi dla każdego pliku wiersz o tym – „Poziom SI: 12
  przypadków granicznych sprawdzonych, 3 odrzucone” – a gdy nic nie
  znalazł do zmiany, stoi tam też o tym informacja. Dotychczas
  najdroższy poziom całkowicie milczał: czy w ogóle był pytany, nie
  dało się rozpoznać z zewnątrz.

  Kto potrzebuje dokładniej, włącza pod „Ustawienia → SI” *Zapisuj w
  dzienniku każde pytanie do SI*. Wtedy plik dziennika zapisuje dla
  każdego pytania rozmiar, czas trwania i liczbę ustaleń, do tego czas
  oczekiwania przez limit ilościowy strony przeciwnej. Przycisk „Pokaż
  plik dziennika” obok otwiera folder – leży w katalogu danych
  aplikacji, który pod Windows jest ukryty i którego samemu nikt nie
  znajdzie. W pliku stoją wyłącznie rozmiary, nigdy tekst z Państwa
  dokumentów.

- **Maskuro rozpoznaje, gdy Państwa usługa SI ogranicza liczbę
  zapytań.** Hostowane usługi dopuszczają często tylko kilka zapytań na
  minutę – cztery to nie rzadkość. Nadliczbowe nie są odrzucane, tylko
  muszą czekać, a z dwóch sekund na odpowiedź robi się czterdzieści. To
  wyglądało dotychczas, jakby model był wolny. Teraz Maskuro odczytuje
  granicę z odpowiedzi usługi, nie wysyła więcej pytań naraz, niż jest
  przyjmowanych, podaje granicę pod „Sprawdź połączenie” i wlicza ją do
  szacunku czasu trwania.

- **Podgląd strony używa Państwa Word, Excel i PowerPoint – i jest przy
  tym około sześciokrotnie szybszy.** Dotychczas potrzebował
  LibreOffice, które stoi na najmniej biurowych komputerów; kto go nie
  miał, widział przycisk domagający się obcej instalacji. Teraz
  obowiązuje: jeśli Microsoft Office jest zainstalowany, jest używany
  sam z siebie – bez konfiguracji, bez pobierania, bez zaznaczania
  czegokolwiek. LibreOffice pozostaje drugą drogą, a przy plikach
  OpenDocument nawet pierwszą; jeśli jedno zawodzi, próbowane jest
  drugie.

  Różnica jest zauważalna przede wszystkim przy pracy: po każdym
  zastąpieniu strona jest ustawiana na nowo, a to kosztuje przez Office
  około pół sekundy zamiast trzech. Pierwszy widok dokumentu trwa nadal
  kilka sekund, potem podąża za Państwa ruchami bez czasu oczekiwania.

  Własny otwarty Word nie jest przy tym dotykany: Maskuro uruchamia
  własną, niewidoczną sesję, otwiera plik tylko do odczytu, wyłącza
  makra i kończy wszystko z powrotem, gdy tylko okno poprawek się
  zamyka. Pliki chronione hasłem są odrzucane, zamiast wisieć w
  niewidocznym oknie dialogowym.

- **Pierwsza konfiguracja pyta teraz też o twarze, kody i podpisy – i
  ładuje wszystko brakujące jednym ciągiem.** Obok rozszerzonego
  rozpoznawania na pierwszej stronie stoją trzy przełączniki obrazowe:
  rozpoznaj i zaciemnij obszary twarzy, rozpoznaj i zaciemnij kody
  kreskowe i QR, zaciemnij odręczne podpisy na stronach PDF. Granica PDF
  stoi widocznie przy znaczniku; pliki Office nie są automatycznie
  przeszukiwane pod kątem podpisów. Pod znacznikami stoi, ile megabajtów
  kosztuje kliknięcie „Dalej”. Ładowanie odbywa się potem w **jednym**
  oknie z **jednym** paskiem postępu nad wszystkim razem, zamiast w
  kilku oknach dialogowych po kolei; przerwanie kończy cały proces i nie
  zostawia niczego w połowie. Kto niczego z tego nie chce, zdejmuje
  znaczniki – wtedy też nic nie jest ładowane.

- **Podgląd można przerzedzić według potrzeby sprawdzenia i zwinąć
  według rodzaju.** Nad listą siedzi suwak *Ukryj dobrze udokumentowane*:
  im dalej w prawo stoi, tym więcej ukrywa od zielonego w kierunku
  czerwonego; całkiem w prawo stoi już tylko to, co program sam zgadł.
  Kliknięcie w nagłówek rodzaju zwija go. Oba są pomocą do czytania, nie
  wyborem – to, co ukryte lub zwinięte, pozostaje zaznaczone i zostaje
  zastąpione; ile jest to akurat wartości, stoi pod suwakiem. Przy
  krótkich listach suwak się nie pojawia. Przełączenie na dwie kolumny
  trzyma teraz ponadto też przełączniki *nigdy więcej*.

- **Lista obrazów może otwierać się sama przed każdym przebiegiem.** Kto
  chce decydować o każdym obrazie osobno, ustawia pod „Obrazy” nowy
  znacznik *Ustalaj pojedynczo przed każdym przebiegiem*. Lista z
  podglądem pojawia się wtedy przy oczyszczaniu sama z siebie, zamiast
  żeby Państwo klikali „Ustal pojedynczo …” za każdym razem sami;
  jeśli ją Państwo przerwą, oczyszczanie też się nie odbywa. Jeśli żaden
  z wybranych plików nie zawiera obrazu, nic się nie pojawia. Domyślnie
  znacznik jest wyłączony.
- **Maskuro znajduje na stronach PDF odręczne podpisy i usuwa je z
  pikseli.** Dotychczas podpis pozostawał pod oczyszczonym dokumentem –
  rozpoznawanie tekstu czyta pismo drukowane, a czego nie czyta, nie
  jest zastępowane. Wyszukiwanie jest osobnym przełącznikiem i potrzebuje
  modelu rozpoznawania, który jest doładowywany jednorazowo.

  Znajduje zmierzonych około 84 ze 100 podpisów i pokrywa je w około
  czterech piątych. To pomoc, nie obietnica: po każdym przebiegu w
  raporcie stoi, ile znaleziono – także wtedy, gdy nie było żadnego,
  bo to może znaczyć, że żadnego nie ma albo że jeden przeoczono. Na 72
  prawdziwych stronach biznesowych bez podpisu żadnego nie wymyślił.

  **Narysowany** podpis jest znajdywany, ale nie usuwany: składa się z
  linii, nie z pikseli, a pas nad nim byłby tylko przykryciem, pod
  którym linie by pozostały. Takie miejsca są liczone i nazywane, żeby
  można je było samemu zaciemnić w oknie poprawek.

  Pliki Word, Excel, PowerPoint i OpenDocument nie są automatycznie
  przeszukiwane pod kątem podpisów. Interfejs, pierwsza konfiguracja,
  pobieranie modelu, wiersz poleceń i podręcznik wymieniają teraz tę
  granicę wyraźnie.

- **Rundgang prowadzi teraz też przez podgląd – okno, w którym Państwo
  decydują.** Przy dokumencie ćwiczeniowym otwiera się sam z siebie,
  nawet jeśli poza tym podgląd jest wyłączony (Państwa ustawienie
  pozostaje takie, jakie jest). Wyjaśniane jest, co znaczą kolory,
  dlaczego w każdym wierszu stoi tylko jedno pytanie – czy w ogóle jest
  tu osoba? – i do czego służy „nigdy więcej”. Przy kolorach światło
  pada na dobrze udokumentowany wiersz, zwykle IBAN – zielony przykład,
  który nazywa zdanie; potem na najsłabiej udokumentowany, i tam mogą
  Państwo w środku wyjaśnienia sami kliknąć: znacznik precz, wartość
  pozostaje w dokumencie. Przy długiej liście okno otwiera się dla
  prowadzenia większe, żeby wyjaśnienie nie leżało na wierszach. Jeśli
  okno otwiera się drugi raz, Rundgang mówi też dlaczego – gotowa strona
  jest jeszcze raz czytana jako obraz, a przy tym powstają fragmenty
  wyglądające jak nazwisko.

- **Edytor otwiera się za pierwszym razem duży.** Oryginał, wynik, pasek
  narzędzi i lista trafień stoją obok siebie i miały w dotychczasowym
  rozmiarze podstawowym za mało miejsca. Kto zmniejszy okno, dostaje
  jego rozmiar następnym razem z powrotem – nikt nie jest przegłosowany.

- **Podwójne kliknięcie w zastępnik przywraca go** – w Word, Excel,
  PowerPoint, OpenDocument, tekście, e-mailu i HTML. A kto przeciąga nad
  kilkoma zastępnikami i wybiera „Przywróć wybór”, przywraca wszystkie
  leżące w środku naraz. Nie trzeba już więc trafiać dokładnie w
  nawias kwadratowy. Zastępniki, które przy anonimizacji stoją za kilkoma
  różnymi wartościami, są z tego wyłączone – są liczone i nazywane, nie
  zgadywane.

- **Podręcznik ma rozdział „Podgląd przed zastąpieniem”.** Okno jest
  domyślnie włączone i jest jedynym, w którym Państwo decydują – w
  podręczniku stało dotychczas tylko w zdaniu pobocznym. Teraz stoi
  tam, co znaczy znacznik (obowiązuje dla **każdego** miejsca
  znalezienia, nie tylko wymienionego), dlaczego na wiersz przypada
  tylko jedno pytanie do odpowiedzi, co „nigdy więcej” trwale powoduje,
  i dlaczego okno przy PDF może otworzyć się drugi raz. We wszystkich
  osiemnastu językach, a na liście ustawień przełącznik jest teraz
  również wymieniony.

### Zmienione

- **Panel „Zastąpione wartości” ma suwak nad kolorami, a tryb nauki już
  tam nie stoi.** Przy więcej niż ośmiu wartościach nad listą siedzi ten
  sam suwak co w oknie podglądu: *Ukryj dobrze udokumentowane* przerzedza
  widok do tego, co naprawdę trzeba sprawdzić. W dokumencie to niczego
  nie zmienia, a ile wierszy z ilu jest widocznych, stoi pod spodem –
  pole wyszukiwania i suwak liczą się razem. Znacznik *Tryb nauki*
  zniknął z panelu; stoi nadal w menu *Narzędzia* i na pasku narzędzi.

- **Panel „Zastąpione wartości” pokazuje teraz te same kolory co
  dokument.** Każdy wiersz w nim ma takie samo tło jak miejsce w
  dokumencie i jak wartość w podglądzie: czerwony znaczy „zgadnięte
  samodzielnie, tu najpierw warto drugie spojrzenie”, zielony „rozpoznane
  przez nazwany wzorzec”. W obrębie każdego rodzaju najniepewniejsze
  stoi na górze – przechodzą więc Państwo listę od góry do dołu i
  najważniejsze widzą jako pierwsze. Dotychczas wszystko stało tam
  jednakowo jasno i posortowane alfabetycznie.

- **Tryb nauki jest fabrycznie wyłączony.** Po korekcie w oknie poprawek
  program pytał dotychczas sam z siebie, czy ma z tego powstać własna
  reguła. To pytanie pojawia się w środku pracy; kto go nie zamawiał,
  odbiera je jako przerwanie. Kto chce mieć reguły, włącza przycisk
  *Tryb nauki* na pasku narzędzi – wybór obowiązuje wtedy trwale, w obu
  kierunkach.

### Naprawione

- **Wyeksportowane pliki reguł są teraz wyraźnie oznaczone jako godne
  ochrony.** Własne pojęcia i wyjątki mogą stać w nich jawnym tekstem;
  ponadto plik może zawierać sól skrótu, którą da się potwierdzić
  przypuszczane wartości. Udany eksport pokazuje dlatego wskazówkę
  ostrzegawczą i wzywa do ochrony pliku i przekazywania go tylko
  świadomie uprawnionym odbiorcom.

- **Ostatnie sprawdzenie bezpieczeństwa nie wstrzymuje już oczyszczonych
  plików biurowych z powodu ich własnych zastępników.** Skrót rodzaju
  jak „SVNR” stoi też w `[SVNR1]`; dotychczas liczyło się to jako rzekoma
  resztka jawnego tekstu i gotowy plik był odrzucany. Jednocześnie
  numery telefonu i IBAN są teraz doczyszczane też tam, gdzie Office
  odkłada tę samą daną bez widocznych spacji w odsyłaczu lub osadzonym
  pliku.

- **Word, Excel, PowerPoint i OpenDocument nie pozostawiają już późno
  odkrytej kopii pola.** Jeśli wartość jest po raz pierwszy rozpoznana w
  schowku pobocznym lub osadzonym pliku biurowym, ciasny przebieg
  końcowy sprząta też wcześniej odczytane widoczne i ukryte kopie. Już
  utworzone zastępniki odsyłaczy nie są przy tym zastępowane po raz
  drugi.

- **Przy pojedynczym przywracaniu listy wyboru Word nie wraca już bez
  pytania sąsiedni wybór.** Pełny akapit oryginału jest przejmowany
  dopiero wtedy, gdy także jego atrybuty nie zawierają już otwartych
  zastępników.

- **Słabo czytelne skany tracą mniej powiązanych danych.** Alternatywny
  odczyt OCR z formą grzecznościową i dwuczłonowym nazwiskiem pozostaje
  zachowany; fragment ulicy, numer domu i kod pocztowy z miejscowością
  chronią razem cały wiersz adresu, nawet gdy rozpada się na sąsiednie
  bloki OCR. Pola faktury i artykułu oraz wiersze wydarzeń obok nie są
  przy tym zabierane. Prawidłowa data rozpadająca się za słowem
  „urodzony” na kilka słów OCR i znaków interpunkcyjnych jest również w
  pełni zaciemniana.

- **Konfetti sukcesu jest teraz widoczne przy automatycznym otwieraniu
  edytora.** Skrawki tryskają bezpośrednio z przycisku *Oczyść* zamiast
  padać deszczem od górnej krawędzi okna. Edytor czeka tylko na
  pierwszy, 850-milisekundowy krótki wytrysk i potem otwiera się
  automatycznie; bez aktywowanego konfetti nadal nie ma opóźnienia.

- **Licznik stron i pasek powiększenia nie skaczą już tam i z powrotem
  przy najeżdżaniu na ikony widoku.** Qt rozdzielał wolną przestrzeń
  wiersza stanu na nowo, gdy tylko pojawiała się tam podpowiedź symbolu.
  Obie grupy obsługi zachowują teraz przy najechaniu swoją naturalną
  szerokość i stałą pozycję.

- **Pomiar prędkości podłączonego serwera SI zawsze się nie
  powodził** – na każdym serwerze, odkąd istnieje własna SI. Pytał z
  wąską granicą odpowiedzi i próbował potem odczytać przez to obciętą
  odpowiedź; to musiało się nie udać, a zapisywano „nie zmierzono”.
  Skutki było widać wszędzie: szacunek czasu trwania liczył Państwa
  serwer z tempem dołączonego modelu na komputerze biurowym, a w
  ustawieniach stało trwale, że prędkość nie jest jeszcze zmierzona.
  Mierzone jest teraz na podstawie ilości, którą serwer wygenerował, a
  nie na podstawie treści jego odpowiedzi.

- **„Maksymalne rozpoznawanie (SI) – wolne” stało tam też wtedy, gdy to
  nie była prawda.** Etykieta i wskazówka opisywały dołączony model na
  komputerze biurowym – „model językowy na tym komputerze”, „przy
  dużych dokumentach do godziny”. Kto podłączył własny serwer SI,
  czytał tam dwie nieprawdy: liczenie nie odbywa się na jego
  komputerze, a odpowiedź przychodzi w sekundach zamiast w godzinach.
  Oba teraz pochodzą z pomiaru. Jeśli go nie ma, aplikacja niczego już
  nie twierdzi, tylko mówi, że jeszcze nie zmierzono.

- **Przywracanie działa teraz też na przeciągniętym zaznaczeniu.** Kto
  przeciągał nad kilkoma zastępnikami i chciał nacisnąć *Przywróć
  wybór*, widział przycisk szary: włączał się tylko wtedy, gdy
  zaznaczenie było **dokładnie** jednym zastępnikiem – przeciągnięte
  przez akapit nigdy nim nie jest. Droga do tego już istniała, tylko
  nikt tam nie docierał. Teraz wystarczy zaznaczyć obszar; wszystkie
  zastępniki w nim wracają jednym ruchem.

- **Przywracanie się zawieszało, gdy lupa porównawcza była otwarta.**
  Lupa zapamiętuje miejsce pod kursorem myszy, żeby podążać za nim w
  oryginale. Przy ponownym wczytaniu po cofnięciu zwracała to miejsce w
  formie, z którą widok tekstu nie mógł nic zrobić – a ponieważ taki
  błąd w środku interfejsu kończy program, z przywracania stawała się
  awaria. Lupa stoi w położeniu podstawowym otwarta, dotyczyło to więc
  zwykłej drogi.

- **Po przywracaniu widok nie skacze już na początek dokumentu.** W
  dłuższym piśmie po każdym ruchu znikało miejsce, przy którym się
  właśnie pracowało. Teraz akapit, który stał na górze, pozostaje na
  górze.

- **Bez LibreOffice podgląd strony mówi, skąd to się bierze, zamiast
  tylko brakować.** Oba przyciski *Podgląd strony* i *Zaciemnij jako
  PDF* były zablokowane i podawały w podpowiedzi tylko, że nie znaleziono
  LibreOffice; drogi do niego nigdzie w aplikacji nie było. Kliknięcie
  otwiera teraz wskazówkę z drogą do bezpłatnego, otwartoźródłowego
  LibreOffice. Podręcznik i FAQ stały w tym miejscu błędnie – zapowiadały
  moduł do doładowania, którego aplikacja nie oferuje.

- **Przed dostarczeniem gotowy plik jest jeszcze raz w pełni
  przeszukiwany – teraz też przy Word, Excel, PowerPoint, LibreOffice,
  e-mailu, HTML i tekście.** Dotychczas tylko PDF miał to ostatnie
  spojrzenie. Wszystkie wcześniejsze sprawdzenia patrzą w miejsce, które
  ktoś wcześniej nazwał; miejsce, o którym nikt nie pomyślał, więc też
  nikt nie sprawdza. Na koniec Maskuro przeszukuje teraz tępo cały
  napisany plik pod kątem wszystkiego, co zastąpił – w każdej części
  pakietu. Jeśli coś pozostaje, **nie** powstaje wynik, a komunikat
  nazywa wartość. Plik uznany za oczyszczony jest gorszy niż żaden
  wynik.

- **Nazwiska stojące w `<script>` i `<style>` są teraz zgłaszane.** Oba
  pozostają nadal nietknięte – tam stoi kod programu, a zastąpienie w
  środku identyfikatora robi z witryny zepsutą witrynę. Nie było to
  jednak dotychczas mówione, i to był błąd: reguła stylu
  `content: "Anna Musterfrau"` stoi odbiorcy **widocznie** na ekranie, a
  w wyniku stała tam dalej, podczas gdy program zgłaszał stronę jako
  oczyszczoną.

- **W ustawieniach można znów wczytywać i usuwać modele dodatkowe.**
  Przycisk obok „Rozszerzone rozpoznawanie” i „Maksymalne rozpoznawanie
  (SI)” kończył się po naciśnięciu w oknie raportu błędu, zamiast
  pobrać model. Druga droga – znacznik w rozpoznawaniu, który sam z
  siebie pyta o model – nigdy tym nie była dotknięta.

- **Nazwiska ukryte w nazwach arkuszy i zakresów tabeli są teraz
  zgłaszane.** Nazwa arkusza stoi na zakładce na dole, nazwa nazwanego
  zakresu w polu nazwy i w każdej formule, która go używa. Zastępowane
  oba nadal nie są – formuły odsyłają przez nie, a skoroszyt z błędami
  odwołań nikomu nie pomaga – ale teraz to tam stoi. Dotychczas komunikat
  pojawiał się tylko dla nazwy arkusza skoroszytu Excel: nazwany zakres
  „Bezuege_Brunnthaler” wychodził cicho razem z plikiem, a przy tabeli
  LibreOffice program milczał całkowicie. Arkusz „Notizen Ortner”
  uchodził przez to za oczyszczony, a pierwsze spojrzenie odbiorcy
  padało na nazwisko.

  Zgłaszane jest przy tym tylko to, co naprawdę prowadzi do osoby: słowo,
  które w tym samym skoroszycie i tak zostało zastąpione, albo trafienie
  wybierające jedno z kilku słów. Samodzielne słowo jak „Zustaendig”
  czy „Bezug_Umsatz” nie wywołuje już ostrzeżenia – wcześniej by je
  wywołało, a ostrzeżenie pojawiające się co drugi skoroszyt po trzecim
  razie nikt już nie czyta.

- **„Przywróć oryginał” przywraca teraz naprawdę wszystko.** W
  niektórych dokumentach brakowało potem pojedynczych znaków – z
  „Seestraße 14” robiło się „Seestraße 4”, z „An:” „An”, z
  „nordlicht-planung” „nordlicht planung” – a pojedyncze wiersze w ogóle
  nie wracały. Dokładnie tam nie dało się potem niczego zaznaczyć myszą
  ani niczego zaciemnić: tekst wprawdzie stał na papierze, ale program
  go już nie znał. Dotyczyło to wąskich znaków – jedynki, dwukropka,
  łącznika – w dokumentach ustawiających każdy znak osobno; dokument
  ćwiczeniowy jest jednym z nich.

- **A te same dokumenty nie są już przy oczyszczaniu zamieniane na
  obraz.** Ponieważ taki znak pozostawał, kontrola zgłaszała resztkę, a
  strona była dla ostrożności rasteryzowana. Tekst na niej był potem już
  tylko odwzorowaniem: nieprzeszukiwalnym, niezaznaczalnym, większym w
  pliku. Dokument ćwiczeniowy pozostaje teraz na obu stronach prawdziwym
  tekstem.

- **Kolorowe znaczniki nie pozostają już nad przywróconym tekstem.**
  Kto cofał zastąpienie, widział kolorowy prostokąt dalej nad
  przywróconym słowem – twierdził „tu coś zostało usunięte”, mimo że
  tam znów stał oryginał.

- **Pas nie zdradza już, jak długie było słowo pod nim.** Przy
  zaciemnianiu pas pokrywa w krótkich wierszach teraz **cały** wiersz –
  blok adresu, dane nagłówkowe, wąską komórkę tabeli. Jeśli cały wiersz
  się nie mieści (zwykły wiersz tabeli z trzema kolumnami), pozostaje
  przy polu; w wierszu tekstu głównego pozostaje dokładnie na słowo, bo
  inaczej nazwisko w środku zdania robiło całe zdanie czarne. A pasy
  stojące jeden pod drugim są **równej długości**: w bloku adresu w
  każdym wierszu stoi wartość, a trzy pasy różnej długości zdradzały
  dalej, jak długie były wiersze. Rosną przy tym tylko tak daleko, jak
  wolny jest papier – przed sąsiednią kolumną pas się kończy.

- **„Cały wiersz” zaciemnia teraz naprawdę cały wiersz.** Dotychczas pas
  kończył się na następnej większej luce – więc na końcu pola. W
  tekście głównym nie było to zauważalne, tam pole jest wierszem; w
  danych nagłówkowych i tabelach owszem: z „Nazwisko: Anna Musterfrau
  Dział: Sprzedaż” powstawał pas kończący się dokładnie na ostatniej
  literze nazwiska – a przez to jego długość znów stała na kartce. Pas
  biegnie teraz od pierwszego do ostatniego słowa wiersza i zabiera
  sąsiednie kolumny. Kto chce trafić tylko wartość, wybiera „Słowa”;
  automatyka zaciemnia bez zmian polami.

- **Przed dostarczeniem gotowy plik jest przeszukiwany po raz ostatni.**
  Wszystkie dotychczasowe sprawdzenia patrzą w miejsce, które ktoś
  wcześniej nazwał – tekst strony, prostokąt znalezienia, powierzchnia
  obrazu. Ale PDF ma więcej miejsc przechowywania, niż da się objąć
  wyliczeniem: adnotacje, wartości formularza, zakładki, informacje o
  dokumencie, załączniki plików, JavaScript. Na koniec Maskuro
  przeszukuje więc tępo napisany plik pod kątem wszystkiego, co
  zastąpił – wszędzie oprócz tekstu strony, gdzie to samo brzmienie
  może też stać dozwolone. Jeśli coś tam pozostaje, **nie** powstaje
  wynik, a komunikat nazywa wartość. Dokument uznany za oczyszczony jest
  gorszy niż żaden.

- **To, czego nie dało się sprawdzić, nie liczy się już jako
  sprawdzone.** Na trzech drogach niepowodzenie kontroli wyglądało
  dotychczas jak czysty wynik. Strona, której warstwy tekstu nie dało
  się odczytać, uchodziła za szczególnie czystą – przecież nie było tam
  nic do znalezienia; jest teraz rasteryzowana. Jeśli strony z
  pozostałym miejscem znalezienia nie dało się zastępczo zrasteryzować,
  była po cichu dostarczana; teraz oczyszczanie woli się przerwać. A
  kontrsprawdzenie w oknie poprawek zgłaszało po własnym błędzie „nic nie
  zostało” – w oknie nie do odróżnienia od tego, że wszystko usunięto;
  teraz pojawia się ostrzeżenie wraz z przyciskiem „Rasteryzuj stronę”.

- **„Resetuj do domyślnych” nie resetowało wcale większości ustawień.**
  Dziewięć z dwudziestu dwóch znaczników stało po tym ruchu bez zmian –
  wśród nich podgląd, „Otwieraj oczyszczone pliki potem”, okno poprawek,
  natychmiastowe odkładanie i oba znaczniki aktualizacji. Zapisany plik
  był wprawdzie opróżniany, ale okno trzymało stare wartości i wpisywało
  je z powrotem przy następnym kliknięciu. Teraz każdy znacznik wraca, a
  uwaga „zmienione” znika razem z nim.
- **„Automatycznie odkładaj raport sprawdzenia przy każdym
  oczyszczeniu” pokazywało się, ale było wyłączone.** Po resecie
  znacznik pozostawał ustawiony, podczas gdy wartość była usunięta – nie
  powstawał już żaden raport, bez żadnej wskazówki na ten temat. To samo
  dotyczyło dziennika sprawdzeń i własnego nagrywania ekranu; ich skrót
  klawiszowy jest teraz przy resetowaniu od razu poprawnie
  zarejestrowany lub wyrejestrowany.

- **Pasy jednego wiersza wyglądają teraz tak samo.** Dotychczas każde
  miejsce znalezienia wnosiło swój własny pas, a jego wysokość
  pochodziła z czcionki trafionego słowa. W wierszu z etykietą i
  wartością w różnych rozmiarach stały przez to obok siebie gruba i
  cienka kreska z przesuniętymi krawędziami, a tam gdzie dwa miejsca
  znalezienia dzieliła tylko spacja, pozostawała nad nimi jasna szpara.
  Pasy tego samego wiersza mają teraz tę samą górną i dolną krawędź, a
  to, co dzieli tylko spacja, staje się jednym pasem. To, co ma
  pozostać między dwoma miejscami znalezienia – przecinek za nazwiskiem,
  etykieta, kwota – nadal je rozdziela. Dotyczy stron składanych jak i
  skanów.

- **Zakładki pod „O tym programie” zaczynają się znów od góry.** Ochrona
  danych, warunki licencji i informacje o licencji otwierały się w
  środku tekstu – kto je czytał, musiał najpierw przewinąć całkiem do
  góry, żeby zobaczyć pierwszy wiersz.

- **Ołówek nie otwiera już drugiego okna edytora, tylko przywołuje
  istniejące na wierzch.** Dotychczas przy każdym kliknięciu powstawało
  nowe. Okno nie ma własnego wpisu na pasku zadań – kto je zminimalizował,
  nie mógł już do niego dotrzeć i klikał jeszcze raz; przy przywracaniu
  okna głównego wszystkie nagromadzone okna wychodziły naraz na wierzch.
  Teraz kolejne dokumenty lądują na pasku zakładek otwartego okna, a
  dokument, który tam już stoi, nie dostaje drugiej zakładki.

- **„Rozszerzone rozpoznawanie” nie nosi już uwagi „zmienione”, dopóki
  brakuje jego modelu.** Dostarczane jest włączone, ale bez
  doładowywalnego modelu nie może nim wcale być – w ustawieniach wiersz
  stał więc na każdym świeżo skonfigurowanym komputerze jako zmieniony,
  mimo że nikt go nie dotknął. Dlaczego znacznik jest wyłączony, mówi
  teraz sama jego etykieta: „Model jeszcze nie wczytany”.

- **Pasek wprowadzenia wyjaśniał w plikach Office i tekstowych płótno
  PDF.** Stało tam „kliknięcie w słowo je zaciemnia” – w pliku Word
  kliknięcie jednak niczego nie zaciemnia, tam się zaznacza, a potem
  naciska przycisk. Mówi teraz, co obowiązuje w danym widoku.
- **Pasek narzędzi był w widoku tekstu zastawiony etykietami.** „Zastąp
  wybór”, „Zaciemnij wybór”, „Przywróć wybór”, „Podgląd strony” i
  „Zaciemnij jako PDF” stoją teraz jako symbol – jak ich rodzeństwo w
  PDF. Ich nazwy pozostają w podpowiedzi i menu.
- **Ctrl+kółko myszy w lupie porównawczej nie poruszało jej suwaka
  powiększenia.** Pismo stawało się większe, suwak i procent obok dalej
  twierdziły stary stan.
- **Instalator aktualizacji nie wychodził na pierwszy plan** – trzeba
  było go najpierw kliknąć na pasku zadań (tylko Windows).
- **Rok na początku wiersza liczył się jako austriacki kod pocztowy.**
  W życiorysie z „2020 Strategie sprzedaży” powstał zastępnik – cały
  wiersz znikał. Czterocyfrowa liczba między 1900 a 2099 potrzebuje
  teraz drugiego sygnału adresowego: ulicy nad nią, słowa pola przed
  nią, oznaczenia kraju lub znanej nazwy miejscowości. Bloki adresowe
  to mają; kolumny lat nie.
- **Para miesiąc-rok liczyła się jako numer telefonu.** Z „Od 08.2010
  123-Verkauft GmbH” powstawał „numer telefonu” – miesiąc, rok i
  pierwsze cyfry nazwy firmy za nim.
- **Raport mówił „sprawdzone przez rozpoznawanie tekstu” i przemilczał,
  czego ono nie czyta.** Jeśli obrazy pozostają zachowane, stoi teraz
  przy tym, że pismo odręczne w nich nie zostanie znalezione – podpis
  lub odręcznie wpisane nazwisko pozostaje. Dotychczas to zdanie stało
  tylko przy zeskanowanych stronach; zwykły PDF z osadzonym podpisem nie
  dostawał o tym ani słowa.
- **Zastępnik na zaciemnionym tle obrazu stał przy lewej krawędzi
  swojego pasa.** Jeśli wartość zostaje znaleziona w obrazie – np.
  wpisany nazwisko obok zeskanowanego podpisu – obszar obrazu musi być
  zaciemniony na pełną szerokość. Krótszy zastępnik pozostawiał obok
  nagą czerń, co wyglądało jak dwa procesy. Stoi teraz wyśrodkowany na
  pasie.

## 0.10.41-alpha.20260826 – 26 sierpnia 2026

### Nowe

- **Po okresie testowym okno przypomina raz na każde uruchomienie o
  licencji.** Pojawia się pięć minut po starcie – nie od razu, żeby nikomu
  nie przeszkadzać przed pierwszym ruchem – i czeka, dopóki trwa
  oczyszczanie. Stamtąd prowadzi droga do zakupu i jedna do wpisania już
  zakupionego klucza; „Później” zamyka okno, gdy tylko upłynie pięć sekund
  w przycisku. Nic nie jest blokowane: darmowy poziom działa dalej jak
  dotychczas.

- **Czas oczekiwania przed przebiegiem w darmowym poziomie trwa teraz
  dziesięć zamiast trzydziestu sekund.** Ma przypominać o licencji, nie
  wstrzymywać pracę.

- **Wszystkie trzy wskazówki dotyczące licencji wyglądają teraz tak
  samo.** Czas oczekiwania, przypomnienie w ostatnich dniach testowych i
  wskazówka po okresie testowym noszą ten sam pasek, tę samą budowę i te
  same przyciski; pozostały czas stoi przy tym w przycisku zamiast jako
  duża liczba obok.

- **Lista trafień w podglądzie stoi znów jedna pod drugą.** Od dziewięciu
  wartości była dwukolumnowa; przy przeglądaniu oko skacze wtedy między
  dwoma torami, a decyduje się tu wiersz po wierszu. Kto lubi dwa tory,
  włącza je z powrotem w lewym dolnym rogu okna – wybór jest zapamiętywany,
  a przy przełączaniu już odznaczone wartości pozostają odznaczone.

- **Poziom SI jest otwarty dla każdego, kto podłącza własny serwer SI.**
  „Ustawienia → SI” zawiera wszystko do tego: podłączenie, co SI wolno
  robić, co ma robić – a nad tym przełącznik dla poziomu wraz z
  kontrsprawdzaniem, gdy tylko wpisany jest serwer. Model językowy, który
  liczy na własnym stanowisku pracy, pozostaje wstrzymany: potrzebuje na
  dziesięć stron kilku minut i nie nadaje się przez to do codziennego
  użytku.

- **Można podłączyć własną SI.** Zamiast dołączonego modelu językowego
  może odpowiadać większy model na innym komputerze – na serwerze
  firmowym lub stacji roboczej z mocną kartą graficzną. Wymagana jest
  usługa z interfejsem zgodnym z OpenAI (Ollama, LM Studio,
  llama.cpp-server, vLLM, LocalAI); konfiguruje się ją pod „Ustawienia →
  Własna SI” wraz ze sprawdzeniem połączenia, które naprawdę odpytuje
  model, mierzy tempo i ustala możliwą formę odpowiedzi. Kilka fragmentów
  tekstu przebiega przy tym równocześnie zamiast po kolei.

- **Co SI wolno robić i co ma robić, jest teraz ustawialne.** Trzy
  przełączniki decydują o sprawdzaniu przypadków granicznych,
  samodzielnym wyszukiwaniu i wyszukiwaniu w tekście głównym; instrukcja
  dla modelu stoi tam dosłownie, da się uzupełnić o pojęcia firmowe i
  zresetować przyciskiem do wartości domyślnej.

- **Jeśli tekst opuszcza przy tym własną sieć, ostrzega się przed każdym
  przebiegiem.** Maskuro rozpoznaje po adresie, czy serwer SI stoi w
  firmie, i nazywa znanego dostawcę po imieniu. Ostrzeżenie da się
  wyłączyć, ale tylko za wyraźnym potwierdzeniem, że jest się uprawnionym
  do tego przekazania, i tylko dla dokładnie tego adresu. Na samym
  procesie to nic nie zmienia: przekazanie pozostaje odnotowane w
  dzienniku i w raporcie sprawdzenia każdego pliku. W wierszu poleceń nie
  ma pytania, tylko zatrzymanie – tam potrzebne jest `--ki-auswaerts-erlauben`.

- **Podgląd przed zastąpieniem jest przy nowych ustawieniach domyślnie
  aktywny i obowiązuje teraz też dla wyraźnie oczyszczonej zawartości
  schowka oraz tekstu i obrazów wklejanych do programu.** Przy pakietach
  dokumentów pojawia się nadal dokładnie jeden podgląd na dokument ze
  wszystkimi stronami; ciche natychmiastowe oczyszczanie krótkich kopii
  celowo nie otwiera okna.

- **Trafienia można włączać i wyłączać w podglądzie na całym kolorowym
  wierszu.** Znacznik jest teraz duży i kontrastowy; dodatkowo pole
  stanu pokazuje „Zastąp” lub przekreślone „Zastąp”, żeby wybrane i
  odznaczone wartości dawały się od razu rozróżnić także na ciemnych
  kolorach pewności.

- **Także pliki PDF z widocznym bezpiecznym kontrspojrzeniem otwierają
  podgląd już tylko raz na dokument.** Odznaczone pojęcia pozostają
  odznaczone dla późniejszego świadka strony; jego sprawdzenie działa
  dalej, bez przerywania tego samego przebiegu drugim oknem dialogowym.

- **Słowa zastępcze wyglądają w edytorze poprawek tak samo także na
  zrasteryzowanych stronach.** Jeśli czerwony zastępnik leży w pikselach
  zamiast w warstwie tekstu PDF, dostaje teraz mimo to tę samą,
  ufarbowaną według pewności powierzchnię tła co zwykły zastępnik
  tekstowy PDF.

- **Już podgląd przed zastąpieniem pokazuje potrzebę sprawdzenia
  znalezionych pojęć.** Każdy wiersz nosi ten sam kolor
  czerwono-pomarańczowo-zielony co później zastępnik w edytorze. W
  obrębie kategorii niska pewność i czerwoni kandydaci fałszywego alarmu
  stoją na górze, silne zielone dowody na dole; remisy pozostają
  alfabetyczne. Jeśli ta sama wartość pochodzi z kilku miejsc znalezienia,
  liczy się dla ostrożności ich najbardziej wątpliwa ocena. Nieocenione
  przypadki szczególne stoją neutralnie żółto między czerwonym a
  pomarańczowym.

- **Wynik można teraz kopiować bezpośrednio z edytora poprawek jako
  plik.** „Kopiuj wynik” umieszcza bieżącą oczyszczoną wersję w schowku,
  bez zamykania edytora i ponownego szukania pliku na głównej liście.
  Przy jeszcze niezapisanej ręcznej obróbce automatycznie przebiega
  najpierw pełna bezpieczna droga zapisu; „Kopiuj obraz” pozostaje
  zachowane jako osobna funkcja dla czystych pikseli.

- **Zastąpione słowa pokazują w edytorze na pierwszy rzut oka, co należy
  sprawdzić najpierw.** Czyste zgadywanie modelu językowego jest
  czerwone, nawet jeśli spaCy zgłasza dla niego ryczałtowo 85 procent.
  Dalsze niepodparte osądy modelu pozostają najwyżej pomarańczowe; silne
  nazwane dowody mogą być zielone. Ręczna praca i starsze
  przyporządkowania bez ocenialnej wartości pozostają neutralnie żółte.
  Także automatyczne pasy zaciemniające noszą te kolory w podglądzie
  edytora – teraz też wtedy, gdy pas jest częścią zrasteryzowanej strony
  PDF. Do tego przyporządkowanie musi pasować, a wcześniejsze pole słowa
  musi być udowodnialnie kryjąco czarne; zwykły pogrubiony druk nie jest
  zabarwiany. W zapisanym PDF wszystkie pasy pozostają niezmiennie
  kryjąco czarne.

- **To, co jest odznaczone w podglądzie, można trwale zapamiętać.** Gdzie
  zdejmują Państwo znacznik, mówią Państwo: tutaj rozpoznawanie się
  pomyliło. Dotychczas dotyczyło to tylko tego jednego dokumentu. Teraz
  przy wierszu pojawia się przełącznik „nigdy więcej”; naciśnięty
  wprowadza wartość trwale na listę „Nigdy nie usuwaj” i obowiązuje odtąd
  we wszystkich dokumentach jako niegroźna. Pod listą stoi, co staje się
  trwałe, zanim naciśnięty zostanie „Zastąp”. Kierunku odwrotnego celowo
  nie ma: to, co raz zostało znalezione, rozpoznawanie znajdzie ponownie.

- **Przycisk resetuje wszystkie ustawienia do stanu wydania.** Stoi w
  lewym dolnym rogu okna ustawień i wcześniej pyta o potwierdzenie.
  Państwa pliki, Państwa licencja, Państwa własne reguły rozpoznawania i
  autostart pozostają nietknięte; to, co narzuca Państwa zarząd,
  obowiązuje dalej. Każde ustawienie odbiegające od stanu wydania nosi
  ponadto uwagę „zmienione” – tak widać na pierwszy rzut oka, co się
  zmieniło.

### Zmienione

- **Wynik nie jest już odkładany sam z siebie – dopiero przy zapisie.**
  Przebieg z okna zapisuje swoją oczyszczoną wersję najpierw w miejscu
  tymczasowym; plik „…_bereinigt” obok oryginału powstaje dopiero, gdy
  naciśnięty zostanie „Zapisz”. Do tego czasu wynik można oglądać,
  poprawiać i kopiować. Każdy gotowy wiersz ma do tego przycisk zapisu,
  pod listą stoi „Zapisz wszystko”, a w edytorze obowiązuje Ctrl+S. Kto
  czyści listę lub kończy program, zostaje zapytany; to, czego nikt nie
  odkłada, nigdzie też nie pozostaje. „Pokaż w folderze” jest zablokowane
  przed zapisem – miejsce tymczasowe nie jest celem, do którego kogoś się
  wysyła. Plik przyporządkowania idzie razem przy zapisie.

  W ustawieniach pod „Program” „Odkładaj wyniki od razu obok oryginału”
  przywraca dotychczasowe zachowanie. Wiersz poleceń, obserwacja folderu
  i strażnik schowka odkładają bez zmian od razu – tam nie siedzi nikt,
  kto mógłby zapisać.

- **Pasek narzędzi edytora poprawek jest uporządkowany.** Tryb nauki
  stoi teraz na prawym końcu przy lupie porównawczej i „Zastąpionych
  wartościach” – trzy przełączniki, które włączają i wyłączają tryb
  pracy, stoją teraz razem. „Zastosuj do wszystkich stron” przesunęło się
  do trzech form zaciemniania, bo tylko tam coś robi. „Kopiuj wynik”,
  „Plik – Resetuj” i „Zastosuj do wszystkich stron” obchodzą się bez
  etykiety; ich nazwa stoi nadal w podpowiedzi i w menu. Między „Zastąp” a
  „Przywróć oryginał” stoi kreska rozdzielająca: oba są kierunkami
  przeciwnymi i wyglądały obok siebie jak dwie odmiany tego samego
  narzędzia.

- **Symbol dla „Kopiuj wynik” pokazuje teraz dokument.** Dwie kartki z
  zagiętym rogiem i wierszami tekstu zamiast dwóch identycznych kartek z
  małą strzałką w rogu. „Kopiuj obraz” nosi w zamian znak obrazu, żeby
  oba dały się rozróżnić bez etykiety. Przycisk „Kopiuj” na liście
  wyników pokazuje ten sam symbol dokumentu – odkłada ten sam plik.

- **Ustawienia są posortowane i opatrzone nagłówkami.** „Rozpoznawanie”
  ma teraz cztery rozdziały: *Co jest usuwane*, *Jak jest zastępowane*,
  *Jak dokładnie jest wyszukiwane* i *Przed i po przebiegu*.
  Rozpoznawanie twarzy i kody kreskowe/QR stoją przy obrazach, gdzie się
  ich szuka; „Program” jest podzielony na *Pliki wynikowe*, *Przy
  starcie*, *Aktualizacja*, *Wyświetlanie* i *Zwrotna informacja do nas*,
  a dodatek do nazwy pliku wynikowego stoi przy plikach wynikowych
  zamiast między językiem a wyglądem.

- **Rozszerzone rozpoznawanie jest fabrycznie włączone**, nawet zanim
  jego model językowy zostanie wczytany. Wcześniej wartość domyślna
  zależała od zasobu modeli, a świeżo skonfigurowany komputer działał
  trwale na słabszym poziomie. Okno konfiguracji oferuje model do
  wczytania na pierwszej stronie i podaje obok cenę. Jeśli go brakuje,
  znacznik mówi to nadal, zamiast udawać poziom, który nie działa.

- **Dwie listy pojęć nazywają się teraz tak, jak działają:** „Zawsze
  usuwaj” zamiast „Własne pojęcia” i „Nigdy nie usuwaj” zamiast
  „Wyjątki”.

- **Okno podglądu jest przejrzystsze.** Od dziewięciu wartości stoją w
  dwóch kolumnach, wiersze są płytsze, a liczba miejsc znalezienia stoi
  bezpośrednio za pojęciem zamiast przy prawym brzegu.

- **W edytorze poprawek Zastąp stoi przed Zaciemnij** – na pasku
  narzędzi, w menu „Narzędzia” i w kliknięciu prawym przyciskiem na
  stronie. Zastąp jest przypadkiem zwykłym: zastępnik da się kliknąć i
  przywrócić, pas nie.

- **Mniej podwójnych przycisków w edytorze.** „Zapisz jako …” i „Kopiuj
  obraz” stoją już tylko w menu Plik, z ich zwyczajowymi skrótami
  klawiszowymi. Na pasku pozostaje po jednym: Zapisz i „Kopiuj wynik” –
  dokąd jest zapisywane, stoi zresztą w wierszu stanu i da się tam
  zmienić jednym kliknięciem.

- **Strażnik schowka nie jest już oferowany przy pierwszym
  uruchomieniu.** Ingeruje w każde kopiowanie w systemie; kto widzi
  program po raz pierwszy, nie może tego ocenić. W ustawieniach stoi
  dalej, tam z klauzulą obok, która do niego należy.

- **Jasny wygląd mniej razi.** Tło okna pochodziło dotychczas z danego
  stylu systemowego i było przez to jedyną dużą powierzchnią, o której
  nikt nie zdecydował – pod Windows niemal biało. Teraz jest to złamana
  biel, taka sama na każdym systemie.

- **Rundgang i podręcznik wyjaśniają kolory.** Co oznaczają czerwony,
  pomarańczowy, zielony i żółty za zastąpionym słowem, stoi teraz jako
  osobny przystanek w Rundgangu i jako akapit w podręczniku – we
  wszystkich wersjach językowych.

### Naprawione

- **Podręcznik i FAQ pokazywały zastępniki, których już nie ma.** Od
  przejścia na krótką formę Maskuro pisze `[NAM1]`; w pomocy stało nadal
  `[NAME1]`, a zdanie „Domyślnie ustawione jest `[NAME1]`” było przez to
  zwyczajnie fałszywe. W siedemnastu przetłumaczonych wersjach stała
  dodatkowo znaczek **niemiecki** zamiast własnego – polski czytelnik
  widział `[NAME1]`, podczas gdy jego program pisze `[NAZW1]`. Podobnie
  końcówka pliku wyniku: tam wszystkie wersje obiecywały `_bereinigt`,
  podczas gdy program tworzy `_limpiado`, `_nettoyé` czy `_除去済み`.
  Dotyczyło to także formy bez numeru (przy anonimizacji wszystko nazywa
  się `[NAM]`, nie `[NAME]`) oraz wyprowadzonego z wartości oznaczenia
  przy funkcji skrótu.

- **Okno podglądu przerywa już tylko raz na dokument – a drugi raz tylko
  wtedy, gdy naprawdę dochodzi coś nowego.** PDF jest czytany z dwóch
  stron: raz ze strumienia treści i na końcu z wyrenderowanej, widocznej
  strony. Dotychczas każda z dwóch pytała osobno. Teraz obowiązuje: to,
  co Państwo zdecydowali w pierwszym oknie, obowiązuje dalej, a wartości,
  które tam już stały, nie wracają. Jeśli natomiast kontrola wzrokowa
  gotowych stron znajdzie coś, czego wcześniej nigdzie nie było, zostaje
  to Państwu przedłożone jeszcze raz – samo, bez już zdecydowanych
  wartości.

- **Okno podglądu mówi teraz, według czego decydować.** Zamiast „Usuń
  znacznik = wartość pozostaje” – co znacznik *robi*, ale nie, kiedy go
  zdjąć – stoi tam: znacznik precz wszędzie tam, gdzie nie stoi żadna
  dana osobowa; tam rozpoznawanie się pomyliło. Ponadto każde okno
  nazywa przebieg sprawdzający, z którego pochodzą jego wartości.

- **Zastępniki wyglądają tak samo w całym dokumencie.** Na stronach
  przebudowywanych drogą OCR jako strony obrazowe widoczne zastępniki
  były dotychczas ustawiane pismem maszynowym – „[PLZ4]” stało wtedy
  szeroko i z szeryfami obok wąskiego „[NAM1]” tej samej strony. Noszą
  teraz to samo pismo bezszeryfowe co wszędzie indziej i nie są już
  ustawiane szerzej, niż planowano przy dopasowaniu. Niewidoczna warstwa
  wyszukiwania zachowuje swoje własne pismo – potrzebuje pewnych
  wymiarów, nie wyglądu.

- **Na pasku narzędzi edytora nie ma już podwójnych kresek
  rozdzielających.** Tam gdzie cała grupa narzędzi odpada dla otwartego
  rodzaju pliku – w PDF-ie np. podgląd strony i renderowanie – obie
  kreski wokół luki pozostawały dotychczas.

- **Przy przywracaniu nie pozostaje już czasami tylko białe miejsce.**
  Już dokładnie przywrócony tekst oryginału nie jest już zamalowywany
  na biało przez szerokie, zbiorcze pole jego usuniętego zastępnika.
  Przy mieszanych przywróceniach tekstu i obrazu tekst jest ponadto
  wstawiany niewidocznie tylko wtedy, gdy obraz strony dokładnie ten
  stan oryginału już widocznie nosi. Dotyczy to ramek, panelu trafień i
  załączników PDF.

- **„Przywróć oryginał” nie proponuje już niepotrzebnie rasteryzacji
  strony.** Surowe sprawdzenie resztki tekstu pozostaje aktywne przy
  zaciemnianiu i zastępowaniu. Przy przywracaniu jest pomijane: tam
  celowo wraca treść oryginału, a niezmienione sąsiednie słowa w
  rozszerzonej ramce przywracania nie były błędem oczyszczania, tylko
  fałszywym alarmem.

- **Rundgang przez edytor wyjaśnia teraz „Zastąp” i „Przywróć oryginał”
  jako osobne kroki.** Oba narzędzia są wyróżniane bezpośrednio na
  pasku i opisują, że wyciągnięta ramka wstawia zastępnik lub przywraca
  pierwotną treść tego miejsca z pliku źródłowego.

- **Także zastępniki charakterystyczne dla kraju pozostają teraz przy
  najwyżej czterech literach.** Te rodzaje brakowały dotychczas w
  centralnym katalogu skrótów i mogły przez to pojawiać się jeszcze
  wypisane w pełni, np. `[UMSATZSTEUER_ID1]`. Nowe przebiegi piszą za to
  `[UID1]`; wszystkie automatycznie rozpoznane rodzaje niemieckie i
  angielskie pozostają przy tym jednoznaczne. Samodzielnie obliczone
  skróty innych języków interfejsu nie rosną już przy zgodności nazwy
  ponad cztery znaki. Własne etykiety reguł pozostają nazwane bez zmian
  tak, jak zostały wpisane.

- **Zastępowanie wykorzystuje teraz całą rzeczywiście wolną przestrzeń
  wiersza, zanim zaciemni.** Dotychczasowa sztywna granica przy
  trzykrotności pierwotnej szerokości słowa tworzyła pasy nawet w
  w dużej mierze pustych polach formularza. Także trafienia widocznego
  kontrspojrzenia OCR dostają teraz przy obsadzonym tekście PDF czytelny
  zastępnik; czarne pozostają czysta zawartość obrazowa, adnotacje i
  wektorowa, wybrany tryb zaciemniania oraz prawdziwe wąskie miejsca, w
  które nie mieści się nawet jednoznaczna krótka forma.

- **Już widoczny zastępnik nie jest przy rasteryzacji bezpieczeństwa
  nadpisywany po raz drugi na czerwono.** Rasteryzacja przejmuje teraz
  istniejący zastępnik z obrazu strony i zakłada tylko niewidoczną kopię
  wyszukiwania. Jeśli pas bezpieczeństwa musi zamalować dokładnie to
  miejsce, odnawiane jest całe rzeczywiste pole zastępnika zamiast tylko
  jego krótszej pierwotnej kotwicy.

- **„Przywróć oryginał” oznacza już tylko bezpieczne cele w wyciągniętej
  ramce.** Wszystkie zastąpione pojęcia w niej rozświetlają się
  pojedynczo i dokładnie; niezmieniony tekst główny pozostaje
  nienaruszony. Prawdziwe wektorowe pasy zaciemniające są również
  oznaczane pojedynczo, gdy pod ich czarną powierzchnią PDF leży tekst
  oryginału. Na zrasteryzowanych stronach podgląd celowo rezygnuje z
  rzekomej powierzchni pasa: wcześniejsze wyszukiwanie pikselowe łączyło
  tam litery, podkreślenia i linie tabel w duże czerwone powierzchnie w
  złych miejscach. Samo przywracanie pozostaje tym nienaruszone.

- **Przy przywracaniu na zrasteryzowanych stronach tekst wraca z
  powrotem.** Ostatnio pozostawało tam puste miejsce z kolorowymi
  prostokątami nad nim. Przywrócony tekst stał w dokumencie, ale był
  zamalowywany przez białe tło zastępnika, rysowane dalej z tyłu w
  budowie strony.

- **Kolory sprawdzenia nie leżą już wielokrotnie na sobie.** To samo
  miejsce było barwione dla każdego wpisu przyporządkowania osobno – na
  jednej stronie pięć prawdziwych miejsc znalezienia, każde pięciokrotnie
  zamalowane, aż z bladego znacznika powstał gęsty blok. I nie pojawiają
  się już na słowach, które w ogóle nie zostały zastąpione: jeśli
  wartość oryginalna nadal stoi na stronie, nie ma tam już żadnego
  znacznika.

## 0.10.40-beta.1 – 24 sierpnia 2026

### Naprawione

- **Pasy zaciemniające w edytorze mają teraz margines bezpieczeństwa.**
  Ramki słów, wierszy i wolne pokrywają teraz też wystające glify i
  wygładzone piksele brzegowe; sprawdzenie renderowania dodatkowo
  zabezpiecza, że nie pozostają ani widoczne resztki, ani odczytywalny
  tekst oryginalny.

- **Teksty zastępcze pozostają czytelne i jednolicie krótkie.** Nowe
  nazwiska, adresy i wolne pojęcia pojawiają się np. jako `[NAM1]`,
  `[ADR2]` i `[BEG3]`. Stała dolna granica wynosi 4,5 punktu; przy braku
  miejsca najpierw skraca się i rozszerza dostępną przestrzeń biegu.
  Stare przyporządkowania z długimi zastępnikami pozostają czytelne i
  możliwe do przywrócenia.

- **Wielowyrazowe zastąpienia z panelu trafień są zabezpieczone przed
  podwójnymi znacznikami i resztkami oryginału.** Test regresyjny
  przechodzi z numerowanymi zastępnikami i bez nich; dla każdego miejsca
  znalezienia zachowywane jest dokładnie jedno wspólne przyporządkowanie.

- **Przywrócona zawartość schowka nie jest na macOS od razu ponownie
  oczyszczana.** Nawet jeśli sygnatura systemowa po zapisie zmienia się
  dopiero z opóźnieniem, Maskuro niezawodnie rozpoznaje własną
  zawartość.

### Nowe

- **Edytor może w pełni zresetować plik do świeżo oczyszczonej wersji
  wyjściowej.** „Plik – Resetuj” odrzuca po potwierdzeniu wszystkie
  poprawki bieżącej karty łącznie z listą zastąpień i licznikami.
  Polecenie jest zablokowane bez zmian i samo daje się cofnąć poleceniem
  „Cofnij”.

- **Przesunięte daty zachowują teraz swoją chronologię niezawodnie w
  wielu plikach.** Wspólne przesunięcie jest już przy włączeniu
  strategii trwale zakotwiczane w regułach; ponadto przesunięcie nie
  może już wynosić zero dni i tym samym niepostrzeżenie pozostawiać
  prawdziwej daty.

- **Ręczna obróbka PDF pokrywa teraz pełny profesjonalny przebieg
  zaciemniania.** Pojedyncze pojęcia, listy i wyrażenia regularne można
  wyszukiwać i bezpiecznie zaciemniać w otwartym PDF-ie lub we
  wszystkich plikach PDF folderu; całe strony i zakresy stron są
  wybieralne bezpośrednio. Kolor, neutralnie biała powierzchnia, tekst
  nakładany, czcionka, wyrównanie i powtórzenie mają podgląd, kody
  wielokrotnego użytku dają się zarządzać oraz importować i eksportować.
  Oczyszczanie PDF usuwa opcjonalnie całą ukrytą zawartość przez pełną
  przebudowę lub wybrane klasy danych. Najbezpieczniejszy wybór jest
  wyraźnie zalecony, nieprawidłowe wzorce wyszukiwania są wyjaśniane, a
  przebiegi folderowe zapisują wyłącznie kopie wyniku.

- **Dobrowolna statystyka użycia pokazuje teraz instalacje i zmiany
  wersji.** Maskuro tworzy do tego losowy, lokalnie zapisywany
  identyfikator instalacji. Nie zawiera on danych urządzenia,
  użytkownika ani licencji; serwer zapisuje tylko jego wartość SHA-256.
  Statystyka pozostaje w pełni wyłączalna w ustawieniach.

- **Rundgang jest teraz prowadzonym ćwiczeniem przez oba okna.** Sam
  wkłada wymyślony dokument ćwiczeniowy na listę, wyjaśnia drogę aż do
  oczyszczenia i po przebiegu kontynuuje automatycznie w edytorze. Kto
  przerywa Rundgang, kończy też tę kontynuację.

- **Firmy z piętnastu dalszych systemów prawnych są rozpoznawane.** Kto
  oczyszcza dokumenty z krajów bałtyckich, Belgii, Skandynawii, Czech,
  Polski, Europy Południowo-Wschodniej, Singapuru, Brazylii lub Meksyku,
  nie traci już nazw firm, ponieważ ich forma prawna była nieznana –
  nowe są między innymi OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k., EIRELI,
  z.s., o.p.s., S.K.A., Pte. Ltd. oraz S.A. de C.V. i S. de R.L.

### Zmienione

- **Paski narzędzi edytora wykorzystują teraz swoje miejsce bardziej
  celowo.** Jednoznaczne symbole standardowe i bezpośrednio rozpoznawalne
  kształty narzędzi stoją bez powtarzającego się tekstu na pasku;
  niejednoznaczne działania zachowują swoją nazwę. Pod „Widok” można
  wyłączyć „Pokaż etykiety narzędzi”, żeby zredukować oba paski w pełni
  do symboli. Podpowiedzi i menu pozostają przy tym w pełni opisane,
  wybór jest zapamiętywany.

- **Tryb nauki jest teraz trwale widoczny na pasku narzędzi.** Można go
  tam bezpośrednio włączać i wyłączać, nawet gdy panel zastąpionych
  wartości jest zamknięty. Pasek narzędzi, menu narzędzi i dotychczasowy
  znacznik w panelu pokazują zawsze ten sam stan.

- **„Resetuj” przy lupie porównawczej resetuje teraz tylko jej
  powiększenie.** Przycisk przywraca wartość domyślną 125 procent, bez
  dokowania lupy, przesuwania jej ani zmiany rozmiaru okna. Za cały
  układ nadal odpowiada „Resetuj widok”.

- **Błędy i życzenia można teraz zgłaszać także przez przycisk pomocy.**
  „Zgłoś błąd …” i „Wyraź życzenie …” stoją tam teraz tak samo jak w
  klasycznym menu pomocy; obie drogi otwierają już istniejące bezpieczne
  zgłoszenie błędu lub publiczną listę życzeń.

- **Menu paska zadań jest krótsze i jaśniej uporządkowane.** Dwa
  polecenia z globalnym skrótem klawiszowym – oczyszczanie schowka i
  zrzut ekranu – stoją teraz bezpośrednio pod sobą ze wspólną prawą
  kolumną skrótów. „Przywróć ostatnią treść oryginału” tam odpada;
  bardziej zrozumiały przycisk przywracania pozostaje dostępny w oknie
  głównym.

- **Strony prawne są dostępne bezpośrednio pod „Pomoc → Kwestie
  prawne”.** Podmenu prowadzi do warunków licencji, oświadczenia o
  ochronie danych, stopki redakcyjnej i regulaminu na maskuro.com.
  Informacje o odstąpieniu od umowy pozostają przy zakupie na stronie.

- **Ręcznie zaciemnione pliki PDF są przy zapisie w pełni przebudowywane
  od nowa.** Widoczne pozostają strony i ich na nowo odczytana warstwa
  wyszukiwania; metadane, załączniki plików, zakładki, komentarze,
  wartości formularzy, ukryte warstwy, indeksy wyszukiwania, skrypty,
  przycięta zawartość i treści ukryte pod innymi obiektami nie są
  przejmowane do pliku wynikowego. Pismo i grafika wektorowa składają
  się potem z pikseli – to jest cena udowadnialnej granicy wobec obcego
  drzewa obiektów PDF.

- **Ctrl+Shift+B robi teraz na wszystkich systemach domyślnie zrzut
  ekranu z Maskuro.** Klawisz Print Screen i kombinacje z nim pozostają
  możliwe jako własne przypisanie. W menu ikony paska zadań globalne
  skróty klawiszowe stoją teraz po prawej stronie obok odpowiednich
  poleceń. Własne zapisane przypisania pozostają zachowane.

- **Edytor uruchamia się ze stronami i lupą porównawczą po lewej.**
  Panel stron stoi u góry, otwarta lupa oryginału bezpośrednio pod nim;
  zastąpione wartości pozostają po prawej. Celowo zapisany własny układ
  ma dalej pierwszeństwo.

- **Dokument ćwiczeniowy nie stoi już trwale w oknie głównym.** Jest
  częścią prowadzonego ćwiczenia i pozostaje dodatkowo dostępny pod
  „Pomoc”.

- **Pierwsze uruchomienie prowadzi bezpośrednio do praktycznego
  ćwiczenia.** Ilustrowana krótka instrukcja nie jest już oferowana jako
  druga, treściowo powtórzona droga wejścia; pozostaje dostępna w każdej
  chwili pod „Pomoc → Krótka instrukcja”.

- **Spoczywająca ikona paska zadań pozostaje w pełnym kolorze.** Pokazuje
  teraz tę samą wyrazistą tarczę Maskuro co aktywny tryb schowka; tylko
  przy aktywnej obserwacji dochodzi zielony świecący punkt.

- **Dokument ćwiczeniowy pozostaje w Maskuro.** Przycisk wejścia tworzy
  wymyślony PDF i wstawia go bezpośrednio na listę plików, ale nie
  uruchamia już dodatkowej przeglądarki PDF.

- **Wyszukiwanie w oknie poprawek pozostaje płynne podczas pisania.**
  Miejsce na licznik trafień jest rezerwowane już przy otwarciu; jego
  pierwszy tekst nie zmienia już płótna i nie wywołuje nowego przebiegu
  rasteryzacji PDF.

- **Nazwy producentów w danych o wyrobie pozostają widoczne.** Wpis jak
  „Wyrób: TRILUX lub równoważny” opisuje potrzebny towar i nie jest już
  zaciemniany jako firma tylko z powodu tej etykiety. Pola dostawcy,
  firmy i producenta pozostają tym nienaruszone.

- **Pomiary korpusu liczą zbyt szeroko zaciemnione trafienia jako
  fałszywe alarmy.** Jeśli Maskuro usuwa oczekiwane nazwisko, ale
  zabiera przy tym część zdania, liczba fałszywych alarmów teraz
  rośnie. Raport wykazuje ponadto przekroczenia osobno; wcześniejsze
  liczby fałszywych alarmów nie są więc bezpośrednio porównywalne.

### Naprawione

- **Techniczne i urzędowe pojęcia z niemieckich dokumentów oryginalnych
  są rzadziej zaciemniane jako nazwiska lub miejscowości.** Wyposażenie
  pojazdów, wiersze pozycji i sum, pojęcia zamówień publicznych i
  ochrony danych, odsyłacze do ustaw oraz nazwy plików materiałów
  publicznych są hamowane tylko w swoim udokumentowanym kontekście
  rzeczowym. Utracony przy rozpoznawaniu tekstu przegłos w „Marz 2026”
  pozostaje chroniony jako miesiąc; „Marz” bez odniesienia do daty może
  nadal być prawdziwym nazwiskiem lub miejscowością.

- **„Przywróć oryginał” od razu przyjmuje pełną potrzebną szerokość.**
  Jeśli ramka trafia tylko jedno słowo przyporządkowanej wartości,
  Maskuro rozszerza ją samodzielnie na podstawie przyporządkowania i
  wiersza oryginału na całą daną – np. z „Planowanie” na „Nordlicht
  Planowanie Sp. z o.o.”. Następnie uchwytna ramka pokazuje także
  rzeczywiście przywróconą pełną szerokość.

- **„Przywróć oryginał” pokazuje teraz czarne pasy jako jednoznaczny
  cel.** Przy najechaniu lub ciągnięciu cały rozpoznany pas świeci na
  czerwono z jasnym konturem kontrastowym, zamiast tylko ledwo
  przyporządkowywalnego pola tekstowego obok. Dotyczy to też
  zrasteryzowanych stron, na których pas składa się już tylko z
  pikseli.

- **Rundgang edytora nie pomija już stacji, gdy panele były zamknięte.**
  Do prowadzenia Maskuro tymczasowo sam otwiera i porządkuje panel
  stron, lupę porównawczą i zastąpione wartości. Po „Gotowe” lub
  przerwaniu wraca osobisty układ. Jeśli narzędzie jest przy danym
  rodzaju dokumentu zasadniczo niedostępne, jego wyjaśnienie pozostaje
  jako przystanek tekstowy, zamiast niepostrzeżenie zniknąć.

- **„Zastąp” pozostaje widoczne także przy zabezpieczającym rozwiązaniu
  rezerwowym PDF.** Jeśli Maskuro musiał przebudować stronę jako obraz z
  powodu pozostałego znaku lub uszkodzonego biegu tekstu, prawidłowe
  zastąpienia stały już tylko niewidocznie w warstwie wyszukiwania, a na
  stronie leżały czarne pasy. Faktycznie ustawione wartości zastępcze są
  teraz zachowywane widocznie czerwono i przeszukiwalnie przez wszystkie
  przebudowy rastrowe i OCR.

- **Wskazówki nad oczyszczoną wersją pozostają czytelne w ciemnym
  wyglądzie.** Nagłówek wersji, wiersz obsługi i wprowadzenie przejmują
  teraz swój kolor pisma bezpośrednio z faktycznie wyświetlanego okna
  Qt.

- **Ramki zaciemniające leżą na zrasteryzowanych stronach PDF znów nad
  tekstem.** Niewidoczne pola słów były w zależności od czcionki
  oryginału węższe niż widoczne litery. Przez to powstawały luki w pasie
  albo ostatnia litera pozostawała czytelna. Pola zachowują teraz
  szerokość, wysokość i kierunek biegu widocznego słowa.

- **„Co nowego” zaczyna się znowu od samej góry.** Okno dialogowe
  changeloga ustawia po zakończonej budowie okna kursor tekstowy i pasek
  przewijania wyraźnie na początek, zamiast, w zależności od wersji Qt,
  zaczynać w środku nowości.

- **Zamykanie podczas rozpoznawania słów skanu pozostaje ciche.**
  Kończący się właśnie przebieg OCR w tle nie wysyła już do już
  zamkniętego okna poprawek.

- **Względne dane czasowe nie są już brane za nazwiska.** Stałe zwroty
  jak „dziś”, „wczoraj”, „jutro” i „przyszły tydzień” Maskuro zna teraz
  z urzędowych danych kalendarzowych odpowiedniego języka dokumentu.

- **Zakończenie podczas pierwszego wczytywania modelu sprząta czysto.**
  Kto zamyka Maskuro lub okno poprawek bezpośrednio po otwarciu, nie
  pozostawia przy usuwaniu procesu wątku wciąż pracującego w natywnym
  rozpoznawaniu mowy. Zapobiega to sporadycznemu raportowi awarii przy
  zamykaniu; już trwające wczytywanie jest porządnie dokańczane.

- **Opóźnione okna dialogowe startu nie pojawiają się już po
  zakończeniu.** Kto zamyka okno główne krótko po starcie, nie dostaje
  potem jeszcze niewidocznie lub z opóźnieniem wyświetlanego pytania o
  najlepsze rozpoznawanie, nowości czy wprowadzenie.

- **HTML i e-mail zachowują swoje zakończenia wierszy.** Na Windows
  serializacja HTML mieszała po oczyszczeniu i przywróceniu LF i CRLF.
  Treść i formatowanie były prawidłowe, ale plik nie był już identyczny
  bajt po bajcie. Pliki HTML i wiadomości MIME przejmują teraz znów
  zapis swojego źródła.

- **Nazwy firm z przyimkiem pozostają kompletne.** Za zaimkiem Maskuro
  ucinał nazwy jak „Gesellschaft für Systemtechnik mbH” czy „Bank für
  Arbeit und Wirtschaft AG” na słowie „für”. Cała nazwa firmy jest teraz
  rozpoznawana; prawdziwe wstępy zdaniowe jak „Jesteśmy ubezpieczeni w
  Alpha Sp. z o.o.” pozostają widoczne.

- **Chińskie nazwy firm pozostają kompletne przed swoją formą prawną.**
  Element marki dający się odczytać jako czasownik mógł mimo
  jednoznacznego dodatku „有限公司” odrzucić całą nazwę. W pismach bez
  wielkich i małych liter urzędowa kotwica formy prawnej ma teraz
  pierwszeństwo przed tą niepewną granicą części mowy.

- **Strony PDF stawały się bez potrzeby obrazami.** Przy wielostronicowych
  plikach PDF, których strony dzielą listę czcionek – co typowe
  generatory tak tworzą – wszystkie kolejne strony po pierwszej traciły
  odniesienie do swoich czcionek. Skutek był podwójny: przegłosy nie
  były już przeszukiwalne w wyniku („Auftragsbestätigung” nie dawało się
  znaleźć), a kontrola uznawała potem litery za przeoczone, które nigdy
  nie stały na stronie – rasteryzowała nienaruszone strony tekstowe na
  obrazy, przez co nie były już przeszukiwalne, niekopiowalne i
  wyraźnie większe. W zbiorze kontrolnym dotyczyło to czterech z
  siedemnastu stron.
- **Sam przecinek nie wywołuje już rasteryzacji.** Jeśli obszar
  znalezienia kończy się na słowie, znak interpunkcyjny obok należy
  jeszcze ledwie do środka. Przecinek czy kropka nie są jednak przeoczoną
  daną, a rasteryzacja kosztuje całą stronę. Litery i cyfry pozostają
  nadal powodem do doostrzenia.

## 0.10.38-alpha.20260824 – 24 sierpnia 2026

### Nowe

- **Nazwy firm bez formy prawnej są teraz rozpoznawane, gdy nazywa je ich
  etykieta.** „Dostawca: Kranzbichler Handels GmbH” było zawsze usuwane –
  forma prawna zdradza firmę. „Dostawca: Dehner Märkte” pozostawało, a w
  ofertach, przetargach i zamówieniach dostawca stoi zwykle dokładnie tak.
  To samo dotyczy „Firma:”, „Producent:”, „Wyrób:”, „Pracodawca:” i ich
  odpowiedników w ośmiu kolejnych językach, i także wtedy, gdy etykieta
  stoi samodzielnie w swoim wierszu, a nazwa pod nią.

  To, co za etykietą *nie jest* firmą, pozostaje nienaruszone: „Dostawca:
  patrz załącznik” nie jest zaciemniane – inaczej stałoby tam „Dostawca:
  [ORGA1]”, a to twierdziłoby nazwę, której nigdy nie było. Etykiety, za
  którymi równie często stoi człowiek („Klient:”, „Zamawiający:”), są
  celowo z tego wyłączone.

- **Wstawiony obraz można teraz też edytować.** W oknie „Oczyść obraz”
  obok „Kopiuj wynik” stoi przycisk *Edytuj w edytorze*: obraz jest
  oczyszczany i potem otwierany do doczyszczania, opisywania i
  wyróżniania – tą samą drogą, którą idzie zrzut ekranu.

- **Numery za swoją etykietą są teraz znajdywane też wtedy, gdy nazywają
  partnera biznesowego.** Dotychczas padały numery klienta, umowy i
  personalny; teraz też numer dłużnika, wierzyciela i dostawcy,
  austriacki numer pracodawcy, rejestracja ANKÖ oraz numer WEEE, EAR i
  EPR producenta – po niemiecku jak i po angielsku. Ponadto Maskuro
  rozumie teraz pisownię ustawionych nagłówków ofert ze spacją przed
  dwukropkiem („Nr klienta : K903944”). Numery artykułu, zamówienia,
  zlecenia, oferty i faktury pozostają nadal nienaruszone: nazywają
  proces lub towar, nie człowieka. Kto mimo to chce je usunąć, odkłada
  je jako własny wzorzec wyszukiwania.

- **Widzą Państwo teraz, jak długo trwało przetwarzanie pliku.** Przy
  gotowym wierszu stoi czas trwania obok rozpoznanego języka („gotowe ·
  niemiecki · 2,4 s”), w podsumowaniu czas całego przebiegu, w panelu
  wskaźników suma – a w raporcie sprawdzenia stoi jako osobne pole. Przy
  kilku plikach wiersz zdradza, który z nich kosztował ten czas.

- **Pisma nieobsługiwane przez OCR systemowe mogą być czytane zastępczo
  przy dostępnym pliku językowym.** Dotychczas obowiązywało: jeśli
  systemowe rozpoznawanie tekstu nie opanowuje pisma (na Macu np.
  dewanagari), w wyniku stało „obraz(y) NIE zostały sprawdzone”, a dane
  na obrazie pozostawały. Teraz wskakuje dołączone rozpoznawanie tekstu,
  jeśli dostępny jest pasujący plik językowy. Ponieważ tak odczytany
  obraz jest mniej pewny niż normalnie sprawdzony, stoi to w wyniku:
  „odczytane metodą zastępczą – proszę sprawdzić”. Zmierzone na
  historycznym stanie pośrednim próby hindi: **o dziesięć danych więcej
  znalezionych i o cztery fałszywe alarmy mniej** (64% → 73%). Aktualna
  wartość końcowa stoi wyżej i nie należy jej z tym mylić.

- **Rozpoznawanie tekstu pyta o właściwy język.** Dla wszystkich języków
  dokumentu poza niemieckim i angielskim używany był dotychczas
  angielski model rozpoznawania, nawet gdy pasujący plik językowy był
  dostępny. Pod Windows dotyczyło to każdego języka – grecki, japoński
  czy hindi były tam czytane modelem angielskim.

- **Asystent konfiguracji przy zupełnie pierwszym uruchomieniu.** (Kto
  już używał Maskuro, go nie dostaje – „pierwsze uruchomienie” oznacza
  pierwsze uruchomienie, nie pierwsze uruchomienie po tej aktualizacji.)
  Trzy pytania zamiast sześciu obrazów: język Państwa dokumentów, czy
  tekst w obrazach ma być doczytywany, i jak chcą Państwo dosięgać
  Maskuro na co dzień. Na końcu pozostają trzy drogi – dokument
  ćwiczeniowy, Rundgang lub ilustrowana krótka instrukcja. Wszystko
  można pominąć, a „Pomoc → Przejdź konfigurację ponownie” przywraca ją.

- **F1 otwiera podręcznik przy pasującym rozdziale.** W oknie głównym, w
  ustawieniach (tam zależnie od strony), w oknie przeglądania i w
  zarządzaniu językami; w oknie poprawek przez Shift+F1, bo F1 pokazuje
  tam od zawsze skróty klawiszowe. Dotychczas pomoc zaczynała się zawsze
  od góry, przy 25 rozdziałach.

- **Nowy pierwszy rozdział podręcznika: „Zacznij w trzy minuty”.** Cztery
  kroki, więcej nie trzeba dla dokumentu – we wszystkich 18 wersjach
  językowych.

- **Rundgang przez okno.** „Pomoc → Rundgang przez okno” kładzie
  światło na jeden element obsługi za drugim i pisze zdanie obok – w
  oknie głównym osiem przystanków, w oknie poprawek siedem. Inaczej niż
  ilustrowana krótka instrukcja wyjaśnia okno, przed którym Państwo
  właśnie siedzą. Przerwanie w każdej chwili klawiszem Esc.

- **Dokument ćwiczeniowy do bezpiecznego wypróbowania.** Pod obszarem
  odkładania stoi teraz „Otwórz dokument ćwiczeniowy” (także w menu
  Pomoc). Tworzy wymyśloną kartkę – nazwisko, adres, numer telefonu,
  IBAN, numer ubezpieczenia społecznego – a na kartce stoi jednocześnie,
  co można z nią zrobić i co potem będzie widać. Ani jedno słowo z tego
  nie należy do prawdziwego człowieka; pierwszy dokument, który
  przepuszczą Państwo przez Maskuro, nie musi więc być prawdziwy.

- **„Tylko sprawdź …” stoi teraz obok „Oczyść”.** Pokazuje, gdzie leżą
  dane osobowe – plik, rodzaj i liczba – bez niczego zmieniania czy
  zapisywania. Kto odłożył dokument, może w ten sposób najpierw
  sprawdzić, zanim oczyści. Dotychczas ta droga leżała tylko w menu Plik
  pod „Przeglądaj folder …” i szła przez cały folder zamiast przez
  odłożone pliki.

- **Jeśli nic nie znaleziono, stoi teraz obok, od czego to może
  zależeć.** Np.: w pliku są obrazy, ale „Sprawdzaj też tekst w
  obrazach” jest wyłączone. Albo: ustawiony język nie pasuje do tego w
  dokumencie. A jeśli nic z tego nie zachodzi, Maskuro mówi też to.

- **Okno poprawek wita Państwa za pierwszym razem trzema zdaniami:**
  kliknięcie zaciemnia słowo, przeciągnięcie obszar, po prawej stoją
  zastąpione wartości. „Zrozumiano” zabiera wskazówkę trwale;
  „Pomoc → Pokaż wprowadzenie ponownie” ją przywraca.

- **Klikanie słów teraz też na zeskanowanych stronach.** Dotychczas
  słowa dawały się klikać tylko tam, gdzie PDF niesie warstwę tekstu –
  przy skanie się nie dało, a w tym samym dokumencie mogło się to
  zmieniać od strony do strony. Takie strony są teraz jednorazowo
  czytane przez rozpoznawanie tekstu; potem klika się słowa jak wszędzie
  indziej. Wiersz stanu mówi, co się właśnie dzieje.

- **Panel stron jest znów powierzchnią.** Kończył się w środku swojej
  kolumny: pasek tytułu obcięty, obok pasek w innym kolorze, a bieżąca
  strona rozpoznawalna tylko po kolorowym polu za jej numerem. Teraz
  wypełnia swoją kolumnę, da się rozciągnąć szerzej, a bieżąca strona
  jest wyróżniona jako cała kafelka – z niezafałszowanym podglądem
  strony w środku.

- **Zastąpione miejsca świecą blado żółto.** W podglądzie strony widać
  dzięki temu na pierwszy rzut oka, gdzie coś zastąpiono – ten sam
  kolor, którego lupa porównawcza używa nad oryginałem. Czerwona ramka
  przy wskazywaniu myszą pozostaje bez zmian.

- **„Resetuj widok” w oknie poprawek** (menu „Widok”). Kto przesunął,
  odczepił lub zamknął panel stron lub listę trafień, ustawia tym
  wszystko z powrotem tam, gdzie stało przy pierwszym uruchomieniu.

### Zmienione

- **Zastępniki są krótsze.** Z `[SOZIALVERSICHERUNGSNR_1]` powstaje
  `[SVNR1]`, z `[ORGANISATION_1]` `[ORGA1]`, z `[EMAIL_1]` `[MAIL1]`.
  Powód nie jest estetyczny: zastępnik dłuższy niż wartość, którą
  zastępuje, rozpycha wiersz i nie znajduje w wąskiej kolumnie tabeli w
  ogóle miejsca – tam pozostawał dotychczas czarny pas, a ten nikomu już
  nie mówi, że w tym miejscu coś stało. Tam gdzie istnieje popularny
  skrót, stoi on (`[BLZ1]`, `[KFZ1]`, `[IBAN1]`). Wyniki z wcześniejszych
  przebiegów pozostają użyteczne: stara pisownia jest nadal rozpoznawana,
  a pliki przyporządkowania z wczoraj działają bez zmian.

- **Symbol programu stoi teraz wszędzie tak samo.** W pasku menu Maca
  pojawiała się dotychczas jednokolorowa tarcza, którą sam system
  barwił na czarno lub biało, na pasku zadań Windows zielona lub szara.
  Teraz każdy pasek nosi tę samą niebieską tarczę Maskuro. To, po czym
  widać, czy schowek jest obserwowany, pozostaje tak samo wyraźne: gdy
  obserwacja działa, przy tarczy siedzi zielona kropka; gdy spoczywa, ta
  sama tarcza stoi blado. Także w najmniejszych rozmiarach stoją teraz
  oba pasy zaciemniające w tarczy – dotychczas pasek zadań pokazywał tam
  tylko jeden.

- **Twarze są rozpoznawane modelem, którego obrazy treningowe powstały
  za zgodą.** Dostarczany jest teraz MediaPipe BlazeFace (Apache-2.0);
  dotychczasowy detektor pozostaje wbudowany i przełączalny, ale nie
  jest już dołączany, ponieważ jego pochodzenie treningowe nie jest
  ostatecznie wyjaśnione. Dla rozpoznawania nic się nie zmienia: na 324
  portretach i 143 obrazach bez twarzy nowa wersja znajduje tyle samo
  przy tyle samo pomyłek i potrzebuje jednej trzeciej czasu.

- **OCR jest kotwicą bezpieczeństwa dla najsilniejszej gwarancji PDF.**
  Zwykły przebieg PDF go używa i tworzy pełną minimalną budowę. Kto
  wyraźnie wyłącza OCR, dostaje bardziej kompatybilną drogę obiektową;
  interfejs, komunikat końcowy i podręcznik mówią teraz wyraźnie, że ta
  droga nie oferuje tej samej architektury przeciw nieznanym ukrytym
  kanałom PDF.

- **Bramka sprzedażowa blokuje teraz też dotychczas dołączony model
  YuNet.** Licencja MIT dokładnej wagi pozostaje udokumentowana, ale nie
  wystarcza dla publicznie widocznego łańcucha danych treningowych przez
  WIDER FACE jako konserwatywne zwolnienie produktu. Przed sprzedażą
  potrzebne jest pisemne wyjaśnienie lub zamiana na model z solidnym
  komercyjnym łańcuchem danych i wag.

- **Nazwy firm i organizacji są teraz usuwane od razu.** Dotychczas
  pozostawały, dopóki nie zażądano ich wyraźnie. To była zła wartość
  domyślna dla listu biznesowego: kto przekazuje ofertę, nie chce w niej
  czytać zamawiającego. „Kranzbichler Handels GmbH”, „Institut für
  Bauphysik” i podobne są dlatego traktowane jak nazwisko. Kto potrzebuje
  inaczej, wyłącza to w oknie; w wierszu poleceń przełącznik nazywa się
  teraz `--ohne-organisationen`. Stary `--mit-organisationen` jest nadal
  przyjmowany i już nic nie robi, żeby istniejące skrypty i skróty się
  nie zepsuły. Dane dat i kwot pozostają bez zmian wyłączone.

- **Zaciemnianie ma teraz trzy formy zamiast dwóch znaczników.** „Słowa”,
  „Cały wiersz” i „Wolna ramka” stoją jako jeden wybór obok siebie –
  obowiązuje zawsze dokładnie jedna. Dotychczas „Wiersze tekstu” i „Cały
  wiersz” były dwoma niezależnymi przełącznikami, oba mogły być
  wciśnięte, a wolna ramka nie była w ogóle przyciskiem, tylko stanem
  wyłączonym pierwszego. Trzy stoją teraz widocznie przy swoim
  narzędziu i są szare, dopóki wybrane jest inne narzędzie.

### Ulepszone

- **Pierwszy dokument jest gotowy o około sekundę szybciej.** Zanim
  oczyszczanie się zaczyna, Maskuro ustala język dokumentu – i pobierał
  do tego dotychczas listy słów wszystkich 48 języków drogą, która
  ładowała znacznie więcej niż same słowa. To było około połowy czasu
  oczekiwania do pierwszego wyniku. Samo rozpoznawanie jest bez zmian:
  widzi te same słowa co wcześniej, tylko szybciej. Każdy kolejny
  dokument i tak tego nie dotyczył.

- **Dokumenty z bardzo długimi akapitami są sprawdzane szybciej.** Przy
  akapicie bez złamania wiersza Maskuro czytał go dla każdego znalezionego
  miejsca od nowa w całości; teraz wystarczy raz. Im dłuższy akapit, tym
  większa różnica – zmierzono około jedną siódmą mniej czasu obliczeń.
  W wyniku nic się nie zmienia.

### Naprawione

- **Wraz z firmą znikało często pół zdania.** Jeśli nazwa firmy stała w
  tekście głównym – „Informacja o Gottwald GmbH & Co KG”, „… (OWU)
  Musterbetriebe GmbH” – zaciemniana była nie tylko nazwa, ale wszystko
  przed nią aż do początku zdania. Tekst stawał się przez to nieczytelny
  i wyglądało to, jakby zaciemniano na oślep. Nazwy firm niosące same
  „für” lub „und” („Bank für Arbeit und Wirtschaft AG”) pozostają przy
  tym bez zmian kompletne.

- **Nazwy firm pozostawały w nagłówkach firmowych, mimo że w tekście
  zostały usunięte.** W ofercie siedziba firmy stała na obrazie
  nagłówka firmowego nadal czytelnie – ta sama miejscowość, którą
  Maskuro zaciemnił w tekście głównym; w przeszukiwalnym tekście wyniku
  stała nawet niewidocznie dalej w środku. To, co raz zostało usunięte,
  jest teraz usuwane też tam, gdzie istnieje tylko jako obraz. Działa to
  też przy logo i znakach słownych narysowanych jako grafika.

- **macOS pytał przy każdym starcie o nagrywanie ekranu**, nawet gdy
  zgoda była od dawna udzielona. Wskazówka przy starcie próbowała
  nagranie, a dokładnie to przywołuje dialog systemowy na ekran. Teraz
  przy starcie pyta tylko sam Maskuro, i tylko raz; system pyta dopiero,
  gdy naprawdę robią Państwo zrzut ekranu.

- **Techniczne pojęcia rzeczowe brano za miejscowości i firmy.**
  „Punkt zasilania”, „Dach płaski”, „Rozdzielnia”, „Podstawa czujki” i
  dziesiątki podobnych słów znikały z ofert i przedmiarów robót. Maskuro
  rozpoznaje je teraz po swoim rdzeniu: to, co kończy się na
  „-instalacja”, „-punkt” czy „-kanał”, jest rzeczą. Nazwy miejscowości
  jak Berlin, Melk czy Wieselburg nie mają takiego rdzenia i pozostają
  nienaruszone – tak samo adresy jak „Der Graben” czy „Alter Markt”.

- **Dokumenty japońskie, koreańskie, chińskie, tajskie i gudźaracki
  mogły spowodować awarię programu.** Jeśli dokument w jednym z tych
  pięciu języków zawierał adres internetowy bez „https://” przed nim,
  oczyszczanie przerywało się błędem wewnętrznym – przy otwartym oknie
  ginęła przy tym też pozostała praca. Wszystkie czterdzieści osiem
  wybieralnych języków dokumentu działają teraz do końca; jeśli dla
  języka brakuje słownika częstości, dana w razie wątpliwości
  pozostaje zamiast znikać.

- **Etykiety pól chroniły tylko po niemiecku i angielsku.** „Reference”
  pozostawało, włoskie „Riferimento” i portugalskie „Referência” były
  usuwane jako dana miejscowości – ta sama nazwa pola, ten sam wiersz,
  inny wynik. Kto nie pracuje po angielsku, był przez to gorzej
  chroniony. Maskuro zna teraz we wszystkich jedenastu pielęgnowanych
  językach te same nazwy pól.

- **„Przywróć oryginał” przywracało na zeskanowanych stronach za
  dużo.** Ramka nad zaciemnionym wierszem bloku adresu odkrywała
  ponownie **cały blok** – a strona pozostawała rozdarta: pozostawały
  resztki pasów, z których sterczały pojedyncze końcówki słów. Powodem
  było to, że pasy leżące jeden pod drugim na zrasteryzowanej stronie
  stykają się i przez to liczyły się jako jedna powierzchnia.
  Przywracany jest teraz dokładnie wiersz, na który wskazuje ramka;
  sąsiednie wiersze pozostają zaciemnione, a pas trafionego wiersza
  znika w całości.

- **Dane ilościowe w listach pozycji brano za adresy.** W wierszu jak
  „1.4 Rów kablowy 100,00 m” „Rów kablowy 100” było zastępowane jako
  ulica z numerem domu. Takie wiersze pozostają teraz nienaruszone;
  prawdziwe adresy – także „Hauptplatz 1, 3250 Wieselburg” – są
  rozpoznawane bez zmian.

- **Przed nazwą firmy znikało pół zdania.** Z „Umowa między firmą
  Gottwald GmbH & Co KG a zamawiającym.” powstawało „[ORGANIZACJA_1] a
  zamawiającym.” – początek zdania zniknął, a z nim wskazówka, o co
  chodzi. Teraz pada tylko sama nazwa firmy. Tam gdzie słowo rodzajowe
  należy do nazwy („Deutsche Bank AG”, „Universität Wien”), wszystko
  pozostaje jak dotychczas.

- **W protokole pozostawały nazwiska mówców, które są jednocześnie
  zawodem.** „Bauer:”, „Koch:”, „Weber:” przed wypowiedzią były
  przeoczane, „Gruber:” obok nie – Maskuro potrzebował dotychczas co
  najmniej jednego rozpoznanego nazwiska w piśmie, żeby w ogóle czytać
  wiersze jako wypowiedzi. Jeśli dokument nosi nagłówek jak
  „Protokół wyników” czy „Protokół”, wystarcza to teraz. Wiersze
  pamiątkowe („Uwaga: …”, „Wskazówka: …”) pozostają nienaruszone.

- **Etykieta pola znikała razem ze swoją wartością.** Z „Projekt: Remont
  i rozbudowa centrum gminnego” powstawał jeden jedyny zastępnik – także
  słowo „Projekt:” znikało, a z nim wskazówka, co w tym miejscu stało.
  Etykiety pozostają teraz. Tam gdzie etykieta należy do danej i niesie
  jej znaczenie („Wewnętrzny 214”), nic się nie zmienia.

- **Maksymalne rozpoznawanie nie sprzątało pojęć rzeczowych.**
  „Dach płaski”, „Punkt zasilania”, „Elektrotechnika” i podobne słowa
  fachowe były zastępowane jako miejscowość lub firma także z
  włączonym poziomem SI – SI nigdy nie dostawała dokładnie tych
  znalezisk do oceny. Teraz sprawdza je również: na korpusie z tekstów
  przetargowych i umownych znikają przez to wszystkie 27 pomyłek, bez
  żeby pozostała choć jedna prawdziwa dana.
  Nazwiska, firmy i miejscowości są rozpoznawane bez zmian.

- **Słowa rodzajowe dla rodzajów placówek brano za organizacje.** W
  tekście umowy znikały „Szkoły wyższe i uniwersytety”, „Szkoły
  państwowe i prywatne”, „Akademickie szpitale kliniczne”, „Placówka
  edukacyjna” i „Firmy dostawcze” – słowa nienazywające konkretnego
  miejsca, tylko rodzaj miejsca. Pozostają teraz. Jeśli stoi przed nimi
  nazwa własna („Komisja Europejska”), zastępowanie działa nadal, a
  nazwy firm w ogóle nie są objęte tą regułą.

- **Nazwiska na listach padały tylko wtedy, gdy były popularne.** Na
  liście uczestników lub obecności pod nagłówkiem kolumny „Nazwisko”
  „Anna Huber” i „Thomas Müller” były usuwane, „Wójcik Aleksandra” czy
  „Kücükgöl Sinan” nie – ten sam wiersz, ta sama budowa. Kto nosi
  rzadsze nazwisko, był przez to gorzej chroniony. Teraz decyduje
  nagłówek kolumny: to, co stoi pod „Nazwisko”, jest nazwiskiem. Lista
  pozycji z rzeczowym nagłówkiem kolumny pozostaje nienaruszona.

- **Numer telefonu za „Wewnętrzny” był przecinany w środku.** Z
  „Wewnętrzny 0732 771190” powstawał „[WEWNĘTRZNY_1] 771190” – druga
  połowa numeru pozostawała czytelna. Teraz cały numer pada w całości,
  a etykieta pozostaje. Prawdziwy numer wewnętrzny („Wewnętrzny 214”)
  jest zastępowany bez zmian wraz z etykietą.

- **Niektórych PDF-ów w ogóle nie dało się już oczyścić.** Jeśli profilu
  kolorów lub metadanych w obrazie nie dało się dowodliwie usunąć,
  przebieg przerywał się bez wyniku – dotyczyło to zwykłych dokumentów
  biznesowych jak strony OWU, specyfikacje wymagań i przetargi. Takie
  pliki są teraz oczyszczane, a ostrzeżenie nazywa miejsca, które
  pozostały otwarte: mogą nieść identyfikator urządzenia, twórcy lub
  nagrania. Oryginał pozostaje jak zawsze nienaruszony.

- **Role umowne brano za osoby.** „Oferent”, „Konsument”, „Najemca”,
  „Kupujący”, „Zamawiającego” i około czterdzieści dalszych słów ról
  było zastępowanych tam, gdzie stały bez rodzajnika – w nagłówkach
  umów, kolumnach tabel i wierszach podpisu. Tekst umowy bez ani jednej
  danej osobowej stawał się przez to miejscami nieczytelny. Te słowa
  pozostają teraz. Jeśli obok stoi wskazówka osobowa – forma
  grzecznościowa, imię, słowo pola jak „Osoba kontaktowa” – zastępowanie
  działa nadal: „Pan Oferent” i „Pani Kupujący” to nazwiska. Częste
  nazwiska rodowe będące jednocześnie zawodami (Bauer, Richter, Koch)
  w ogóle nie są objęte tą regułą.

- **Skrócona nazwa ulicy była przeoczana, gdy numer domu przyklejał się
  bezpośrednio do kropki.** „Schlesischestr.31” nie liczyło się jako
  adres – a ponieważ kod pocztowy obok czerpie swoje oparcie ze
  znalezienia adresu, on też pozostawał. W wyniku adres z ulicy i kodu
  pocztowego dawał się z powrotem złożyć, i to tylko na niektórych
  stronach tego samego dokumentu. Oba padają teraz razem. Oznaczenia
  rzeczowe z doczepioną liczbą („Kabelrinne200”) pozostają nienaruszone.

- **Adres na dwóch wierszach był ściągany w jeden jedyny zastępnik.**
  Jeśli w bloku adresu kod pocztowy stał nad ulicą, Maskuro łączył oba
  wiersze w jedno miejsce znalezienia: w wyniku znikało złamanie
  wiersza, a kod pocztowy pozostawał czytelny przed nim. Teraz każdy
  wiersz jest znajdywany i zastępowany osobno, a układ pisma pozostaje
  zachowany. Ta sama przyczyna czasami wciągała też nazwisko z wiersza
  powyżej do adresu.

- **Maksymalna droga PDF nie przejmuje już obiektów oryginału.** Przy
  włączonym rozpoznawaniu tekstu Maskuro buduje każdą stronę od nowa
  całkowicie z widocznego obrazu PDFium. Do nowego pliku minimalnego
  wchodzi tylko ta strona obrazowa i nowo utworzona, ograniczona do
  tekstu OCR warstwa wyszukiwania – nie obce drzewo obiektów z
  komentarzami, załącznikami, akcjami, warstwami, metadanymi, profilami
  kolorów czy kluczami prywatnymi. Dotyczy to też treści w wyglądach
  adnotacji, wzorach, czcionkach typu 3, obiektach formularza i
  maskach miękkich. Plik źródłowy pozostaje nienaruszony.

- **Twarze i kody w zagnieżdżonej grafice PDF były przeoczane.** Oba
  detektory widzą teraz dodatkowo pełny wyrenderowany obraz strony.
  Dzięki temu portrety i kody QR/kreskowe w adnotacjach, wzorach,
  glifach typu 3 i maskach przezroczystości docierają do detektorów;
  rozpoznane obszary są – jeśli włączone – zaciemniane przed budową
  minimalną. Samo wykrywanie pozostaje omylne.

- **Brakujący silnik OCR kończył się przy PDF błędem wewnętrznym.**
  Maksymalny przebieg przerywa się teraz kontrolowanie i bez pliku
  docelowego, zamiast wydawać niepełny lub niesprawdzony plik.

- **Kilka prawdziwych wartości kontaktowych i biznesowych przepadało,
  podczas gdy zastępowany był tekst rzeczowy.** Pola nazwisk przez
  złamania wiersza, nazwy banków i firm, formy prawne, opisane numery
  identyfikacyjne, daty urodzenia oraz granice telefonu, URL i IBAN są
  ciaśniej sprawdzane. Jednocześnie kraje w tekście rzeczowym, słowa
  ról i rodzajowe, kody artykułów/norm, kolumny liczb i zwykłe skróty
  częściej pozostają nienaruszone.

- **Mieszane i obrócone wiersze OCR były źle czytane.** Niepewne słowa
  pionowe są teraz lokalnie prostowane i doczytywane; techniczne
  wartości łacińskie w tekście niełacińskim dostają niezależnego
  świadka angielskiego. Samodzielna niepewna pojedyncza cyfra jest
  poprawiana tylko wtedy, gdy zgadzają się dwa ciasne ciągi cyfr.
  Polskie formy prawne w formie OCR „sp. z 0.0.” są w zamkniętym
  kontekście czytane jako „sp. z o.o.”.

- **Pomiar obrazu mógł przeoczyć częściowo widoczne resztki wartości.**
  Sprawdza teraz nakładające się lokalne wycinki, rozróżnia białe pismo
  zastępnika na czarnym pasie od glifów oryginału i przenosi surowe
  pola obrazu też na obrócone, na nowo wyrenderowane minimalne PDF-y.
  Stały syntetyczny korpus główny osiąga dzięki temu 1392/1392
  usuniętych wartości docelowych przy 0 fałszywych alarmach i 0 błędach
  przetwarzania. To jest dowód korpusowy, nie ogólna obietnica 100%.

- **Niekomercyjne modele językowe nie są już oferowane.** Sześć
  włoskich i greckich wariantów spaCy na licencji CC BY-NC-SA 3.0
  zostało usuniętych z katalogu, pobierania i drogi wczytywania; także
  już istniejące foldery modeli są ignorowane. Oba języki używają
  zamiast tego wielojęzycznego modelu na licencji MIT.

- **Nazwisko pod „Osoba kontaktowa” było usuwane tylko w połowie.**
  Jeśli etykieta stoi samodzielnie w wierszu, a pod nią „Nazwisko Imię”,
  imię pozostawało, gdy było jednocześnie zwykłym słowem – z „Mayer
  Roman” powstawało „[NAZWISKO_1] Roman”. Takie wiersze są teraz
  brane w całości. Dział w tym samym miejscu („Dział techniczny
  wewnętrzny”) pozostaje nadal nienaruszony. Przy okazji naprawione:
  „Osoba kontaktowa” w ogóle nie liczyła się jako pole nazwiska, mimo że
  „Kontaktperson” zawsze się liczyło.

- **Nazwa firmy bez formy prawnej pozostawała, gdy między nią a formą
  stało słowo branżowe.** „Kranzbichler Handels GmbH” było usuwane,
  nagie „Kranzbichler” trzy akapity dalej nie – przy „Kranzbichler GmbH”
  za to tak. Teraz działa oba. Zwykłe słowa są z tego wyłączone:
  „Deutsche Bank AG” nie robi ze słowa „niemiecka” w tekście firmy.

- **Ta sama wartość nazywała się w tym samym dokumencie raz nazwiskiem,
  raz miejscowością.** „Anna Musterfrau … Musterfrau” dawało
  „[NAZWISKO_1]” i „[MIEJSCE_1]” – w drugim miejscu brakuje imienia, a
  bez niego powstała miejscowość. Usunięte było oba, ale czytało się to
  jak dwie różne rzeczy. Wartość zachowuje teraz oznaczenie swojego
  pierwszego wystąpienia.

- **Daty nie były już usuwane.** Data w całości z cyfr („01.03.2026”)
  odpadała od ostatniego wydania przez sprawdzenie pomyślane dla
  nazwisk i pozostawała w dokumencie – także w trybie „przesuń”, i bez
  wiersza w raporcie sprawdzenia. Dotyczyło to tylko tych, którzy
  wyraźnie włączyli daty.

- **Kraje i kontynenty nie są już zaciemniane.** „Dostawa idzie do
  Stanów Zjednoczonych”, „Słabość rynku w Azji”, „norma obowiązuje w
  Rumunii” – takie dane niczego nie mówią o osobie i pozostają teraz.
  Jeśli nazwa kraju należy jednak do adresu lub stoi za etykietą jak
  „Miejsce zamieszkania” czy „Miejsce urodzenia”, jest nadal usuwana.
  **Miasta nie są tym dotknięte** – „Jestem właśnie w Bilbao” pozostaje
  daną o osobie i jest nadal zaciemniane.

- **Skrócone słowa stawały się adresami internetowymi.** Jeśli w
  tekście stoi „bzw. deutsche” lub „incl. der”, niektóre PDF-y dostarczają
  kropkę bez spacji – powstawało z tego „bzw.de” lub „incl.de”, ważny
  adres z końcówką krajową, i było usuwane. Takie pary słów pozostają
  teraz. Prawdziwe adresy nie są tym dotknięte, nawet bez „www.” przed
  nimi.

- **Kolumny liczb z bilansów były zaciemniane jako numery telefonu.** W
  sprawozdaniach biznesowych i tabelach cen rok poprzedni i bieżący stoją
  obok siebie – „64.518 65.133”. Liczyło się to jako jeden numer telefonu
  i było usuwane, podobnie jak zakresy liczbowe jak „12200-23200” i data
  z następującą liczbą. Takie liczby pozostają teraz. Odwrotnie
  prawdziwy numer telefonu jest rozpoznawany pewniej: etykiety
  „Telefon”, „Faks”, „Komórka”, „Wewnętrzny” i ich odpowiedniki w
  innych językach interfejsu liczą się teraz też – dotychczas program
  rozpoznawał tam tylko angielskie słowa.

- **Nazwiska w numerowanej tabeli pozostawały.** Lista uczestników lub
  tabela personalna w typowej formie – nagłówek kolumny, pod nim „1.1
  Auersperg Bernhard Montaż 03.03.2026” – w ogóle nie była oczyszczana:
  takie wiersze wyglądały jak lista pozycji oferty, w której pojęcia
  rzeczowe mają pozostać. Jeśli nagłówek kolumny nosi etykietę osobową
  („Nazwisko”, „Imię i nazwisko”, „Surname” …), wiersze pod nim liczą
  się teraz jako nazwiska. Listy pozycji pozostają bez zmian oszczędzone
  – także wtedy, gdy w nagłówku firmowym stoi „Osoba prowadząca sprawę:”.

- **Z nazwiska powstawały czasem dwa zastępniki obok siebie.** Jeśli
  nazwisko rodowe stało też samodzielnie w dokumencie, obróbka wtórna
  zastępowała w miejscu jak „Anna Musterfrau GmbH” najpierw nazwisko, a
  potem imię – w wyniku wyglądało to jak dwie różne osoby. Teraz
  wygrywa najdłuższe znane nazwisko.

- **Wymyślone wartości nie stały w żadnym przyporządkowaniu.** Kto
  wybrał „Wymyślaj wartości”, dostawał wynik, w którym „Anna Musterfrau”
  stawała się „Greta Mayrhofer” – w przyporządkowaniu nic o tym nie
  stało, gdy tylko w tym samym dokumencie występowało choć jedno
  anonimowe zastąpienie. Przez to żadnej wymyślonej wartości nie dało
  się przywrócić, a plik przyporządkowania przemilczał zastąpienie.
  Najbardziej delikatne było trzecie: kto czyta wynik, widzi
  wiarygodne nazwisko i nie ma żadnej wskazówki, że jest wymyślone.
  Teraz każde zastąpienie stoi w przyporządkowaniu.

- **Przyporządkowanie nazywało zaciemnione „zastąpione”.** E-mail
  dzieli przyporządkowanie ze swoimi załącznikami, a załącznik może być
  zaciemniony, podczas gdy tekst maila nosi zastępnik. W przyporządkowaniu
  stało wtedy dla wszystkich trzech miejsc to samo – „zastąpione” – a
  przywracanie szukało w załączniku zastępnika, którego tam nie ma: pas
  pozostawał. Teraz przy każdym miejscu znalezienia stoi, co tam
  naprawdę się stało, i oba załączniki wracają.

- **Wartości stojące tylko w obrazie nie dawały się przywrócić.** W
  panelu trafień stały podwójnie – raz jako zastępnik, którego nigdzie
  nie było w dokumencie („Zastępnik nie został znaleziony w dokumencie”),
  raz jako miejsce zaciemnione. Pierwszy wiersz był czystą księgowością
  i zniknął.

- **Zaciemnione wartości dawały się przywrócić tylko raz.** Jeśli ta
  sama wartość stoi w kilku miejscach, jedno kliknięcie przywraca
  wszystkie – pozostałe wiersze pozostawały jednak w panelu trafień, a
  następne kliknięcie na nie zgłaszało „Niejednoznaczne”. Teraz znikają
  razem.

- **Przywracania brakowało w dzienniku sprawdzeń, gdy tryb nauki był
  wyłączony.** Kto przywracał przywróconą wartość w oknie poprawek, nie
  znajdował tego procesu w dzienniku sprawdzeń, gdy tylko pytania
  nauki były wyłączone – dowód zależał od przełącznika, który dotyczy
  tylko propozycji reguł. Przy włączonym dzienniku sprawdzeń pytanie o
  powód jest teraz zadawane niezależnie od tego, a wiersz zapisywany.

- **Wciągnięte pliki pozostawały nieoczyszczone – i nawet nie były
  zgłaszane.** Kto przeciąga plik do dokumentu zamiast wysłać go jako
  załącznik, Word lub PowerPoint odkłada go w całości w dokumencie. Stał
  potem niezmieniony w wyniku, wraz ze swoją pierwotną nazwą pliku i
  ścieżką odkładania – a te w praktyce często same niosą nazwisko. Takie
  pliki są teraz oczyszczane jak reszta dokumentu.

- **A tam, gdzie się nie da, Maskuro to mówi.** Jeśli w osadzonym
  obiekcie tkwi stary format (Word 97, Excel 97), dla którego nie ma
  oczyszczania, pojawia się teraz komunikat UWAGA z nazwą pliku.
  Dotychczas był po cichu przekazywany niezmieniony.

- **Rozerwane słowa i skróty brano za nazwiska.** Jeśli słowo w PDF jest
  rozdzielone na końcu wiersza, przy odczycie niektórych plików
  powstaje fragment – „Jahresent… gelts”, „Gewerbli…”. Takie fragmenty,
  posklejane słowa („TürverschlussmitV”) i nagie skróty („JY”, „FFB”)
  były zaciemniane, jakby były nazwiskami. Pozostają teraz. Nazwisko z
  tym samym uszkodzeniem podziału pozostaje nadal zaciemniane, dopóki
  jest przy nim forma grzecznościowa – a nazwiska, które z natury noszą
  wielką literę w środku słowa (McKenzie, MacDonald, LeBlanc), i tak nie
  są tym dotknięte.

- **Wartości miar i miesiące liczyły się jako adres.** W dokumentacji
  technicznej zaciemniane były „2000 luksów”, „1200 Mbit”, „1500 W”,
  „5308 miejsc” i „2022 marca” – cztery cyfry i słowo wielką literą
  wyglądały jak kod pocztowy z miejscowością. Kod pocztowy liczy się
  teraz tylko wtedy, gdy jest przy nim też sygnał adresowy: oznaczenie
  kraju, etykieta pola, początek wiersza, ulica w wierszu powyżej lub
  miejscowość, którą tam widzi też rozpoznawanie języka. W pięciu
  przedmiarach robót znika przez to 14 błędnych zaciemnień, bez żeby
  pozostał prawdziwy adres.

- **Dokładniejsze rozpoznawanie zastępowało za dużo.** Dołączalny
  poziom „dokładniejsze rozpoznawanie” brał w niemieckich dokumentach
  biznesowych pojęcia rzeczowe za nazwiska i miejscowości –
  „Instalacja fotowoltaiczna”, „Punkt zasilania”, „Dach płaski”,
  „Wejście personalne” – i zaciemniał oznaczenia firm z bieżących list
  pozycji. Powodem było oszczędzanie: ich trafienia były wyłączone ze
  sprawdzeń rozpoznających wiersz pozycji lub spisu. To oszczędzanie
  obowiązuje teraz już tylko dla nazwisk wieloczłonowych, dla których
  istnieje ten poziom – „Anna Huber” w wierszu spisu pozostaje więc
  rozpoznawana, pojedyncze słowo rzeczowe w wierszu pozycji odpada.
  W przetargu technicznym połowi to fałszywe zaciemnienia poziomu, bez
  utraty żadnego nazwiska.

- **Wykresy niosły ze sobą swoje pełne dane źródłowe – niesprawdzone.**
  Kto wstawia w Word lub PowerPoint wykres, program odkłada tabelę, z
  której był liczony, jako osobny plik w dokumencie. Widoczne są z tego
  tylko te kilka liczb na wykresie; w tabeli stoi cała lista, wraz z
  wierszami, które na wykresie w ogóle nie występują. Ta tabela była
  dotychczas przekazywana niezmieniona. Jest teraz oczyszczana razem, z
  tymi samymi zastępnikami co reszta dokumentu.

- **To samo dla osadzonych obiektów w plikach OpenDocument** (ODT, ODS,
  ODP): wstawiony wykres lub wstawiona tabela pozostawały nienaruszone.

- **Dokumenty Word: przypisy dolne i końcowe nie były oczyszczane.**
  Ich tekst pozostawał w pełni w wyniku – także nazwiska, adresy i
  numery kont. Dotyczyło to każdego dokumentu Word z przypisem dolnym
  lub końcowym. Podobnie pozostawał nienaruszony blok autotekstu
  podróżujący niewidocznie z dokumentem.

- **Word: dane w listach wyboru, komentarzach i opisach obrazów.**
  Wpisy pola wyboru (widoczne dopiero po rozwinięciu), autor komentarza,
  opis rysunku i adres za poleceniem odsyłacza pozostawały dalej w
  wyniku.

- **Excel: tabela przestawna niosła dane źródłowe po raz drugi.**
  Skoroszyt z tabelą przestawną przechowuje w niej pełną kopię
  analizowanych wierszy – niewidocznie, ale w pliku. Ta kopia
  pozostawała dotychczas niezmieniona, nawet gdy w samym arkuszu
  wszystko było zastąpione. Dotyczyło to każdej analizy przekazywanej z
  tabelą przestawną.

- **Excel: komentarze konwersacji i ich autorzy.** Tekst komentarza
  nowszego typu i katalog komentujących – nazwa wyświetlana i
  identyfikator logowania, w firmach zwykle adres e-mail – pozostawały
  dalej w wyniku. Ten sam katalog w dokumentach Word również.

- **Samodzielnie zdefiniowane właściwości dokumentu w Word i Excel.**
  Pola jak „Klient” czy „Sygnatura akt”, które kancelaria dodaje do
  swoich szablonów, nie były dotychczas oczyszczane. Nie są widoczne w
  żadnym widoku, a mimo to wędrują z każdą kopią.

- **Arkusze (ODS): lista wyboru komórki.** Jak w Excelu od poprzedniego
  wydania, teraz też w tabelach OpenDocument oczyszczane jest to, co
  pojawia się przy rozwinięciu komórki. Odniesienia do innych komórek
  pozostają przy tym nienaruszone, żeby lista dalej działała.

Wszystkie te miejsca dają się jak zwykle przywrócić przez przyporządkowanie.

- **Wiadomości Outlook: uszkodzony plik kończył oczyszczanie twardo.**
  Pewne popsute pliki `.msg` prowadziły do przerwania zamiast do
  komunikatu; teraz są czytane, o ile są czytelne.

- **Plik przyporządkowania jest teraz czytelny tylko dla Państwa.**
  Zawiera dane oryginału jawnym tekstem i leżał dotychczas z
  zwyczajowymi uprawnieniami obok wyniku – na wspólnym zasobie mógł go
  otworzyć każdy. Sam oczyszczony wynik pozostaje bez zmian; przecież ma
  być przekazywany dalej.

- **Doładowane modele językowe są przed rozpakowaniem dokładniej
  sprawdzane.** Zmanipulowany pakiet – np. z udostępnienia firmowego, z
  którego obsługiwanych jest kilka stanowisk – mógł przy rozpakowywaniu
  odkładać pliki poza przewidzianym folderem. W zwykłym doładowywaniu
  nic się nie zmienia.

- **Zrób zrzut ekranu – i od razu jest oczyszczany.** Klawiszami
  `Ctrl+Shift+B`, przez „Plik → Zrób zrzut ekranu …” lub przez symbol na
  pasku zadań przeciągają Państwo ramkę nad ekranem. To, co w niej leży,
  idzie potem tą samą drogą co każdy inny plik: rozpoznawanie tekstu
  czyta tekst ekranu, nazwiska, adresy, numery telefonu i adresy e-mail
  są zaciemniane, a potem obraz stoi otwarty w edytorze, gdzie mogą
  Państwo ramką doczyścić to, co przeoczono. Oczyszczony obraz ląduje na
  pulpicie (lub w Państwa ustawionym folderze wyjściowym); **surowy**
  zrzut nigdzie nie jest odkładany i jest usuwany przy zamknięciu.
  Rozpoznawanie tekstu jest dla tego przebiegu włączane, nawet gdy
  poza tym jest wyłączone – na obrazie bez niego nic by się nie
  znalazło. Na Macu system pyta za pierwszym razem o zgodę „Nagrywanie
  ekranu”.

- **Na obrazach można teraz rysować: prostokąt, elipsę, strzałkę, tekst
  i numerowane znaczniki kroków.** W sześciu kolorach i trzech
  grubościach kreski, wybieralnych klawiszami od 1 do 5. Pomyślane jest
  to dla zrzutów ekranu i instrukcji: pokazać, o co chodzi, bez
  otwierania do tego drugiego programu. Cofnięcie i doregulowanie
  uchwytami działają jak przy każdym pasie – adnotację da się więc
  przesuwać i rozciągać po jej postawieniu.
  **Rysowanie wyraźnie nie jest zaciemnianiem.** Narysowany prostokąt
  jest ramką, nie pasem: to, co jest pod nim, pozostaje czytelne i
  wychodzi razem z plikiem. Do usuwania danych nadal służą „Zaciemnij” i
  „Pikselizuj”; narzędzia rysunkowe stoją dlatego w osobnym wierszu
  paska narzędzi, a wiersz wskazówki mówi to, dopóki jedno z nich jest
  wybrane.

- **Edytowany obraz trafia jednym kliknięciem do schowka.** „Kopiuj
  obraz” w edytorze (lub `Ctrl+C`) odkłada go takim, jaki stoi –
  wklejenie wystarcza, żeby przenieść go do wiadomości lub maila. Droga
  od naciśnięcia klawisza do czatu ma dzięki temu cztery kroki i nie
  potrzebuje folderu.

- **Do tego zakreślacz, cień i gradienty.** „Wyróżnij” barwi powierzchnię
  bez jej zakrywania – treść pod nią pozostaje czytelna, i dokładnie
  tym różni się od pasa. „Cień” odróżnia adnotację od niespokojnego tła,
  „Gradient” pozwala kolorowi rozmyć się w kierunku ciągnięcia; oba
  obowiązują dla wszystkich sześciu narzędzi rysunkowych.

- **Naprawione, zanim kogoś to dotknęło:** nowy wiersz narzędzi
  wyglądałby u każdego, kto już korzystał z Maskuro, niemal pusto –
  zapamiętany podział okna pochodził sprzed tego czasu i nie zostawiłby
  mu miejsca. Przestarzały podział jest teraz odrzucany; okno edytora
  stoi wtedy jednorazowo w swoim podstawowym układzie.

- **Własny zrzut ekranu da się wyłączyć.** Kto jest przyzwyczajony do
  Greenshot, ShareX lub narzędzia wycinania, wyłącza pod „Ustawienia →
  Program” „Rób zrzut ekranu z Maskuro”. Maskuro w ogóle wtedy nie
  rejestruje skrótu klawiszowego – pozostaje dla Państwa narzędzia – a
  zmiana obowiązuje od razu, bez ponownego uruchomienia. Oczyścić taki
  zrzut da się nadal: Ctrl+V pobiera go ze schowka do okna.

## 0.10.37-alpha.20260821 – 21 sierpnia 2026

### Nowe

- **Przy anonimizacji każde miejsce znalezienia nosi teraz swój własny
  numer.** Dotychczas wszystkie osoby nazywały się `[NAZWISKO]`,
  wszystkie miejscowości `[MIEJSCE]` – przez to nie dało się już
  powiedzieć, które miejsce należało do której wartości, i nie było nic
  do przywrócenia. Teraz numery liczą dalej dla każdego wystąpienia: to
  samo nazwisko stoi w trzech miejscach jako `[NAZWISKO_1]`,
  `[NAZWISKO_3]` i `[NAZWISKO_7]`. W dokumencie nadal nie widać, które
  miejsca do siebie należą – ale z plikiem przyporządkowania da się
  przywrócić każde z osobna. Plik przyporządkowania jest dlatego znów
  wybieralny też przy anonimizacji; proszę przechowywać go osobno od
  wyniku.
- **Miesiące, dni tygodnia, waluty, jednostki i formy prawne firm we
  wszystkich 48 językach dokumentu nie liczą się już jako nazwiska lub
  miejscowości.** Nazwy kalendarzowe i jednostek pochodzą z Unicode CLDR
  (generowane, nie pisane ręcznie), formy prawne z prawa spółek
  poszczególnych krajów – także wieloczłonowe („sp. z o.o.”, „Pty Ltd”) i
  poprzedzające („株式会社”). Tam gdzie nazwa miesiąca jest jednocześnie
  imieniem (Maj, Sierpień), decyduje budowa: z dniem lub rokiem obok –
  data, inaczej – imię. Do tego formy grzecznościowe i tytuły, całe
  formuły pożegnalne, rodzaje dokumentów i rzeczowniki podstawowe ulic
  dla 28 języków z własnym modelem językowym, skróty ustaw (RODO, UStG,
  ABGB, § 6 Abs 1 Z 27 UStG) oraz nazwy języków jako wartość pola
  („Język: niemiecki”). Listy stoją pod „Pomoc → Listy słów …”.
- **Indie: adres i kod PIN są rozpoznawane** – „15 गांधी मार्ग”, „नई
  दिल्ली 110001” tak samo jak „15 Gandhi Marg, New Delhi 110001”. Pakiet
  kraju Indie znał dotychczas tylko numery identyfikacyjne; w
  dokumentach hindi adresy przez to pozostawały.
- **Każdy oczyszczony plik biurowy jest przed przekazaniem jeszcze raz
  otwierany jako pakiet.** Wyciąg tekstu nie zauważa, gdy Word, Excel
  lub LibreOffice odmówiłyby otwarcia pliku (podwójny wpis, urwany XML,
  brakująca część). A liczone jest wobec oryginału to, czego
  oczyszczanie nigdy nie może zmienić: strony PDF, arkusze, wiersze i
  komórki tabeli, slajdy prezentacji. Jeśli próba się nie powiedzie, w
  wyniku i w raporcie sprawdzenia stoi ostrzeżenie UWAGA – oryginał
  pozostaje niezmieniony.
- **Także automatyka zaciemnia całe pole.** W trybie zaciemniania pas w
  krótkich wierszach – blok adresu, komórka tabeli, dane nagłówkowe –
  pokrywa cały wiersz zamiast tylko znalezionej wartości: pas o
  długości słowa zdradza, jak długie było słowo. Etykieta i kwoty obok
  pozostają; wiersze tekstu głównego (dłuższe niż połowa szerokości
  tekstu) są nadal zaciemniane dokładnie na słowo, żeby nazwisko w
  środku zdania nie robiło całego zdania czarnym.
- **Przywrócone wygląda znów jak w oryginale.** „Przywróć oryginał” i
  „Cofnij zastąpienie” w edytorze PDF wpisują teraz obszar dokładnie z
  powrotem z pliku źródłowego – ta sama czcionka, ten sam rozmiar, ten
  sam kolor i położenie, na skanie te same piksele. Do tej pory tekst
  był wstawiany na nowo czcionką zastępczą i wyglądał rozpoznawalnie
  odtworzony. Pas wcześniejszego zaciemnienia znika przy tym w całości,
  zamiast być zamalowywany na biało – kolorowe tło komórki w tabeli
  pozostaje zachowane. Dotyczy to też obróconych stron, tekstu z
  osadzonych obiektów formularza i **wypełnionych pól formularza**: na
  zrasteryzowanej do tego kopii roboczej wraca wycinek z na nowo
  wyrenderowanej strony oryginału – także tam, gdzie żadna warstwa
  tekstu nie zna wartości pola. Także **zastąpione obrazy** w PDF wracają
  w ten sposób – spikselizowane, rozmyte lub w całości usunięte, w
  całości lub tylko wyciągnięty wycinek. Tylko tam, gdzie plik źródłowy
  już nie leży obok wyniku, pozostaje przy dotychczasowej drodze.
- **Zaciemnione i bez zastąpienia usunięte wartości można przywracać
  też w Word, Excel, PowerPoint i OpenDocument.** Dotychczas przywracanie
  potrzebowało tam zastępnika w tekście – pas lub luka nie miały drogi
  powrotnej. Teraz panel trafień oferuje wiersze „zaciemnione” i
  „usunięte”, gdy tylko nietknięty plik źródłowy leży obok wyniku:
  Maskuro porównuje wynik z oryginałem i wstawia wartość z powrotem w
  miejsce pasa lub luki – wraz z formatowaniem, rozdzielony przebieg
  staje się znów całością. Dotyczy to też tekstu, HTML, e-mail i
  załączników biurowych e-maila; jeśli tekst maila nosi zastępnik, a
  załącznik pas, oba są przywracane jednym ruchem.
- **Także załączniki PDF e-maila lub wiadomości Outlook da się
  przywracać** – zastępniki (numerowane i anonimowe), pasy i bez
  zastąpienia usunięte. Bez płótna miejsce pochodzi z oryginalnego
  załącznika; wartość wraca dokładnie co do glifu, w kolejności odczytu
  oryginału.
- **Zamaskowane wartości da się przywracać** – w PDF i w widoku tekstu.
  Maska („**** **** **** **** 3201”) nigdy nie jest jednoznaczna, dwa
  numery noszą tę samą; dlatego przywracanie nigdy nie idzie drogą
  dosłowną, tylko pyta oryginał, jaka wartość stała w tym miejscu.
  Dotychczas te wiersze w panelu trafień w ogóle nie były obsługiwalne.
- **Osadzone obrazy w Word, Excel, PowerPoint i OpenDocument da się
  przywracać.** Wartość zaciemniona w obrazie wraca przez swój wiersz
  panelu – Maskuro czyta obraz oryginału i przywraca dokładnie to
  miejsce; obraz rozmyty, usunięty lub obrobiony twarzami i kodami
  przywraca nowy wpis „Przywróć osadzone obrazy” w menu Edycja jako
  całość z pliku źródłowego – także przez załączniki biurowe e-maila lub
  wiadomości Outlook. Obraz stojący sam jako załącznik i zaciemniony
  przez rozpoznawanie tekstu wraca tak samo przez swój wiersz panelu.
- **Wymyślone wartości da się przywracać w widoku tekstu.** Dotychczas
  panel zgłaszał tam „Niejednoznaczne”. Teraz przywracanie szuka
  wartości w oryginale i wymaga w tym samym miejscu wyniku dokładnie
  wymyślonego zastępnika – wymyślone nazwisko nigdy nie jest dosłownie
  zastępowane wszędzie, mogłoby gdzieś stać naprawdę.
- **Przywracanie w Word, Excel, PowerPoint i OpenDocument zachowuje
  formatowanie oryginału.** Jeśli wartość stała przez kilka przebiegów –
  „Anna” zwykłym pismem, „Musterfrau” pogrubione i czerwone – wracała
  dotychczas w całości do pierwszego przebiegu i traciła pogrubienie i
  kolor. Teraz znaki rozdzielają się z powrotem jak w oryginale; akapit
  Word jest potem bajt w bajt pierwotny. To samo dotyczy stron HTML,
  części HTML e-maila i treści HTML wiadomości Outlook (.msg) – przy
  e-mailu pozostaje ponadto zachowany doctype, który oczyszczanie
  dotychczas po cichu usuwało.
- **Pliki tekstowe zachowują swoje kodowanie.** Oczyszczanie i
  przywracanie zapisują teraz `.txt`, `.md` i `.csv` w kodowaniu, w
  jakim zostały dostarczone – UTF-8 z BOM i bez, UTF-16, Windows-1252.
  Dotychczas plik Windows-1252 stawał się zawsze UTF-8, a plik UTF-16
  wracał uszkodzony, nawet gdy nie było w nim nic do zastąpienia.
- **Przywrócone obrazy zachowują swój tryb koloru.** Skan w skali szarości
  wraca jako skala szarości zamiast trzy razy większego pliku RGB,
  paleta jako paleta, czarno-biały jako czarno-biały – dla całego obrazu
  z tymi samymi wartościami co w oryginale. Dotyczy plików obrazów i
  obrazów w PDF. CMYK i 16 bitów pozostają RGB, bo wynik PNG nie potrafi
  unieść żadnego z nich.
- **Ramka na obrazie przywraca całą obróbkę, której dotyka.** Spikselizowane
  twarze noszą margines wokół rozpoznanego pola; kto ciągnął ramkę tylko
  nad twarzą, zachowywał spikselizowany pierścień. Teraz ramka rośnie na
  spójną zmianę wobec oryginału – wystarczy ramka nad partią oczu.
  Oddzielne pasy obok pozostają; przy w całości usuniętym lub w całości
  rozmytym zdjęciu obowiązuje nadal wyciągnięta ramka. Dotyczy plików
  obrazów i obrazów w PDF.
- **Pasy zaciemniające przez cały wiersz.** W trybie wierszowym edytora
  pas biegnie teraz od pierwszego do ostatniego słowa wiersza, nie tylko
  nad trafionym słowem – pas o długości słowa zdradza, jak długie było
  słowo, a z sześciu znaków przed kodem pocztowym da się odgadnąć nazwę
  miejscowości. Etykiety, kwoty i kolumny tabeli obok wartości pozostają
  – pas pokrywa pole, nie wiersz faktury. Nowy przełącznik „Cały wiersz”
  obok „Wiersze tekstu” przełącza z powrotem na dokładnie na słowo, gdy
  sąsiednie słowa mają pozostać; wybór jest zapamiętywany.

### Naprawione

- **Obrazy na stronach HTML i w e-mailach pozostawały niesprawdzone –
  nazwisko w logo stało po oczyszczeniu nadal czytelne.** Obraz osadzony
  na stronie (adres ``data:``) w ogóle nie był dotykany, tylko jego tekst
  alternatywny; logo w gałęzi HTML maila (obraz inline bez nazwy pliku)
  odpadało przez filtr załączników; a przy nazwanym załączniku obrazu
  reguła obrazu „rozmyj”/„usuń” pozostawała bez skutku. Teraz wszystkie
  trzy idą tą samą drogą co plik obrazu: rozpoznawanie tekstu w
  zachowanym obrazie, twarze, kody, metadane i reguła obrazu. Raport
  wymienia obrazy – także ostrzeżenie, gdy pozostają niesprawdzone bez
  rozpoznawania tekstu – a „Przywróć osadzone obrazy” oraz przywracanie z
  panelu trafień znają teraz też te obrazy.
- **Pliku biurowego z obrazem w ogóle nie dało się oczyścić, gdy
  rozpoznawanie tekstu nie opanowywało języka.** Na Macu czyta systemowe
  rozpoznawanie tekstu; dla hindi, greckiego, chorwackiego czy
  litewskiego nie potrafi tego i od niedawna też to mówi – przy Word,
  Excel, PowerPoint i OpenDocument przerywało się jednak przez to **całe**
  oczyszczanie, i nie powstawał żaden plik. A tekst dał się oczyścić
  bez zarzutu; tylko obraz nie był czytelny. Teraz plik jest zapisywany
  jak przy PDF i pojedynczych obrazach, a w wyniku stoi, że obrazy NIE
  zostały sprawdzone – z powodem i odsyłaczem do „Zarządzaj językami”.

- **W skoroszytach Excel nazwiska pozostawały na listach wyboru.**
  Lista pola rozwijanego (weryfikacja danych) jest teraz oczyszczana jak
  każda inna zawartość komórki; odniesienia do zakresów komórek
  pozostają nienaruszone, żeby skoroszyt pozostał cały.
- **Tam gdzie zastępnik nie pasował, stał czarny pas – teraz stoi tam
  krótsza pisownia.** `[URODZ_1]` zamiast `[DATA_URODZENIA_1]`, a dopiero
  gdy nawet najkrótsza forma nie pasuje, jest zaciemniane. Pas nikomu
  już nie mówi, że coś tam stało; krótki zastępnik to mówi. Edytor
  poprawek potrafił to już, samoczynne oczyszczanie dotychczas nie. Plik
  przyporządkowania prowadzi obie pisownie do tej samej wartości, żeby
  dało się przywrócić też skrócone.
- **Pierwsze kliknięcie „Zastąp” pozostawiało okno poprawek chwilę bez
  reakcji.** Rozpoznawanie nadające zastępnikowi jego rodzaj (`[NAZWISKO_3]`
  zamiast `[POJĘCIE_3]`) było wczytywane dopiero w tym momencie – około
  dwie do trzech sekund. Jest teraz przygotowywane w tle przy otwieraniu
  okna; zmierzono, że z 2289 milisekund powstało 193.
- **Dwa równoczesne oczyszczania mogły dwukrotnie wczytywać ten sam
  model językowy** – np. obserwacja folderu i okno główne. Ponieważ
  każdy model zajmuje kilkaset megabajtów, zapotrzebowanie na pamięć
  stało wtedy krótkotrwale przy podwojeniu. Teraz drugi przebieg czeka
  na model pierwszego.
- **Miejscowość w wierszu daty jest teraz usuwana też wtedy, gdy model
  językowy sam jej nie rozpoznaje:** to, co jest pewnie znalezione jako
  kod pocztowy z miejscowością („3335 Amstetten”), ciągnie swoją nazwę
  miejscowości w całym dokumencie – jak nazwisko z pełnego imienia i
  nazwiska. A skrót z cyfrą przed nazwiskiem („T3 Hofbauer Christian”)
  pozostaje czytelny, zamiast zniknąć razem z zastępnikiem.
- **Zamknięto trzy przecieki z drugiego odczytu prawdziwego zlecenia:**
  osoba prowadząca sprawę „T3 Hofbauer Christian” liczyła się z powodu
  skrótu „T3” jako nagłówek kolumny i pozostawała czytelna; miejscowość,
  którą model językowy przez złamanie wiersza wciągnął w nagłówek
  kolumny, połykała „Pos.” i zostawiała imię klienta; a nazwisko wraz z
  formą grzecznościową („Pan Robert Köttel”) ciągnęło tylko nazwisko,
  nie imię – a za to każde „Pan”. Skróty są teraz czystymi literami,
  nazwiska dwuwyrazowe nie są nagłówkiem, trafienia są ucinane przed
  nagłówkiem kolumny, a forma grzecznościowa nie liczy się do nazwiska.
- **Miejscowość w wierszu daty („Melk, 05.08.2026”) bezpośrednio pod
  blokiem adresu pozostawała czytelna.** Model językowy sklejał ją z
  miejscowością wiersza kodu pocztowego w jedno trafienie, a to padało w
  całości wobec wzorca kodu pocztowego. Teraz wystająca reszta pozostaje
  osobnym trafieniem. Znalezione dzięki nowemu drugiemu odczytowi wyniku
  (`werkzeuge/zweitlesung.py`).
- **Mac: skan w języku, którego systemowe rozpoznawanie tekstu nie
  opanowuje (np. hindi, grecki, chorwacki, litewski), uchodził za
  sprawdzony.** Czytany był rozwiązaniem rezerwowym angielskim, obce
  pismo pozostawało w obrazie, a raport mówił „nic nie znaleziono”.
  Teraz stoi „obraz(y) NIE zostały sprawdzone” z powodem, a zarządzanie
  językami nie obiecuje już dla takich języków rozpoznawania tekstu
  tylko dlatego, że leży plik językowy Tesseract.
- **W PDF znak interpunkcyjny za zastąpionym słowem pozostaje.** Z
  „Przyjęcie dnia 01.03.2026, wypis dnia 04.03.2026.” powstawało
  dotychczas „Przyjęcie dnia [DATA_1] wypis dnia [DATA_2]” – przecinek i
  kropka końcowa brakowały, przy zastępnikach tak samo jak przy
  przesuniętych datach. Usuwana jest teraz tylko rozpoznana wartość, nie
  całe słowo aż do następnej spacji; przecinek, średnik, kropka lub
  nawias za nią pozostają na swoim miejscu, a zastępnik nie przechodzi
  przez nie.
- **Rosyjski i ukraiński działały niepostrzeżenie na słabszym modelu
  wielojęzycznym**, gdy brakowało pakietu pomocniczego do analizy form
  wyrazowych (`pymorphy3`) – własne modele nie dawały się wtedy wczytać,
  a „Львів” stawał się osobą. Do rozpoznawania nazwisk analiza form
  wyrazowych nie jest potrzebna; model jest teraz wczytywany bez niej, a
  miejscowości są znów miejscowościami.
- **Informacje o licencji w 16 językach były na starym stanie.** Stało
  tam jeszcze, że kod źródłowy MPL jest udostępniany „na żądanie”, QPDF
  uchodził za MPL-2.0, w tabeli brakowało siedmiu komponentów (wordfreq,
  Qt, ONNX Runtime, tokenizers, zxing-cpp, llama.cpp, YuNet), akapit
  spaCy był po angielsku, a na końcu wisiał angielski rozdział zastępczy.
  Teraz wszystkie 18 wersji stoi na stanie niemieckiej: archiwa źródłowe
  trwale pod maskuro.com/quellcode/oss/, QPDF Apache-2.0, droga
  Qt-LGPL, pochodzenie modeli. Także angielska tabela ma brakujące
  wiersze.

- **Słowa umowne w dopełniaczu („des Angebotsinhaltes”, „des Anbotes”,
  „des Terminplanes”) nie liczą się już jako miejscowość.** Pojedyncze
  słowo za rodzajnikiem dopełniacza lub celownika z końcówką fleksyjną
  jest rzeczownikiem pospolitym – nazwy miejscowości się nie odmieniają
  („do Grazu”). Jeśli miejscowość stoi gdzie indziej w dokumencie bez
  rodzajnika („Burgenland”), pozostaje rozpoznawane też „des
  Burgenlandes”.
- **Przesunięte, zamaskowane i wymyślone wartości rasteryzowały stronę
  PDF.** Kontrola po usunięciu dopuszczała w prostokącie znalezienia
  tylko zastępnik w nawiasach kwadratowych; przesunięta data
  („01.07.2026”) lub zamaskowana wartość („****1234”) liczyła się jako
  przeoczona reszta, a strona była dla ostrożności zamieniana na obraz –
  przy „Zastąp” nie. Teraz takie strony pozostają tekstem, a przywracanie
  z panelu lub ramki znów dostarcza oryginał.
- **Wielowyrazowych wartości zastępczych nie dało się w PDF przywracać
  przez panel trafień.** Wymyślone nazwisko („Greta Mayrhofer”) lub
  zamaskowany IBAN („**** **** **** **** 3201”) składa się z kilku
  słów; wyszukiwanie miejsc znalezienia porównywało słowo po słowie i
  zgłaszało „Zastępnik nie został znaleziony w dokumencie”. Teraz
  następujące po sobie słowa tego samego wiersza są odczytywane razem.
- **Po przywróceniu bez zastąpienia usuniętej wartości jej wiersz
  panelu pozostawał.** Wartości usunięte przez strategię „zaciemnij” w
  trybie zastępnika bez zastąpienia nie mają zastępnika, po którym panel
  mógł zmierzyć zniknięcie. Teraz wiersz jest przekreślany, gdy tylko
  wartość znów stoi w dokumencie.

- **Skróty złożone jak „E-Helfer” czy „U-Bahn” nie liczą się już jako
  nazwisko.**
- **Resztki dzielenia wyrazów („Leis-”) i za długie złożenia
  („Bauarbeitenkoordinationsgesetzes”, „Baustellenkoordinator”) nie
  liczą się już jako nazwisko lub miejscowość.** W zeskanowanym tekście
  przetargowym zaciemniano przez to o 28 słów mniej.
- **Listy pozycji zeskanowanych ofert nie liczą się już jako spis
  nazwisk.** Dodatkowy przebieg dla spisów (krótkie wiersze) robił z
  „rura chłodnicza” i „urządzenia zewnętrzne” osoby; teraz wyłącza się,
  gdy tylko numery pozycji jak „1.1.5” stoją na początku wiersza.
  Wiersze dat w wątkach mailowych nie liczą się przy tym jako numery
  pozycji.
- **Nagłówki kolumn i numery pozycji zeskanowanych ofert („Poz.”,
  „Poz. 1.1.3”, skróty „E/L/S”) liczyły się jako nazwisko lub
  miejscowość.** Skrót sam na swoim wierszu, etykieta wraz z numerem i
  pojedyncze litery wierszami nimi nie są.
- **Strona „oddychała” w oknie poprawek po otwarciu lupy porównawczej**
  – przy „Szerokość strony” i „Dopasuj” skala zależy od okna widoku, a
  to zmienia się z każdym paskiem przewijania, który się pojawia lub
  znika; każda kolejna czynność przesuwała stronę o kawałek dalej.
  Płótno dociąga to teraz samo, aż się ustabilizuje. A przyciski
  powiększenia, suwak i skróty klawiszowe trzymają środek obrazu także
  wtedy, gdy przy powiększaniu pojawia się pasek przewijania.
- **Skany zapisane w poprzek są teraz czytane prosto, a drobny druk w
  dużych skanach nie ginie już.** 24-stronicowa zeskanowana oferta
  zachowywała w każdej stopce sześć czytelnych IBAN-ów banku, numer
  rejestru handlowego i UID: skan leżał w PDF obrócony o 90°, a
  rozpoznawanie tekstu przy bardzo dużych obrazach pomijało w zależności
  od wymiarów całe wiersze. Teraz widoczny obrót jest uwzględniany, a
  duże obrazy są czytane w nakładających się pasmach – stopki są
  czarne.
- **Ulice nazwane po osobach z łącznikiem przed rzeczownikiem
  podstawowym („Josef Admanseder-Straße 7”, „Abt-Karl-Straße 8”,
  „Dr.-Karl-Renner-Straße 12”) są rozpoznawane jako adres.** W nagłówku
  firmowym zeskanowanej oferty taki adres pozostawał czytelny, bo wzorzec
  wymagał spacji przed „Straße”.
- **IBAN-y z rozpoznawania tekstu, które niosą O zamiast 0 lub l zamiast
  1, są teraz rozpoznawane.** W drobnym druku skanu rozpoznawanie tekstu
  chętnie czyta cyfry jako litery; numer miał wtedy formę IBAN, ale suma
  kontrolna się nie zgadzała, i pozostawał. Jeśli suma kontrolna zawodzi,
  próbowany jest teraz odczyt z cyframi – jeśli wtedy się zgadza, to jest
  IBAN. Błędne cyfry kontrolne pozostają błędne.
- **Fragmenty zdań jak „następujących kodów na” liczyły się jako
  miejscowość.** Nazwisko lub miejscowość zaczynające się od słowa małą
  literą nim nie są – z wyjątkiem partykuł szlacheckich („van Gogh”,
  „de Vries”).
- **W edytorze obok pasa zaciemniającego pozostawała ostatnia
  litera** („…6”, „…t”, „…g”), a pas miał wysokość wyciągniętej ramki
  zamiast wiersza. Przyczyna: gdy edytor nie mógł zmierzyć strony,
  uważał każdą ramkę za „nie trafiono słowa” i stosował ją dokładnie –
  bez reguły, że połowa słowa nigdy nie pozostaje. To samo zdarzało się
  przy pojedynczych poleceniach tekstowych, których edytor nie mógł
  umiejscowić. Teraz obok zawsze liczy się pole słowa: to, co ramka
  istotnie nakłada, pada w całości.
- **Ostatnia litera słowa wystawała poza pas zaciemniający.** Pas był
  wymierzany według szerokości przesunięcia z metryk czcionki; jeśli
  czcionka rysuje glif szerzej, jego reszta stała obok pasa. Pole znaku
  obejmuje teraz też narysowany glif.
- **Komunikat o zamianie strony na obraz obiecywał za dużo.**
  „Wygląd pozostaje taki sam” nie jest prawdą po rasteryzacji: pismo i
  grafika stają się wtedy pikselami, plik robi się większy. Komunikat
  mówi to teraz – i podaje też drugi powód rasteryzacji (przebudowa
  uszkodziłaby stronę).
- **Tekst za usuniętą wartością przesuwał się o do jednego punktu w
  lewo.** Przy przebudowie wiersza początek był mierzony na krawędzi
  glifu, kontynuacja od punktu pióra – szerokość przesunięcia pierwszej
  litery pozostawała jako błąd („C” 0,5 pt, „I” 1,0 pt). Teraz przebudowa
  liczy konsekwentnie od punktu pióra; dalsza część zdania stoi co do
  dziesiątej punktu na swoim miejscu.
- **Austriacki UID z odstępami („ATU 187 35901”) i numer rejestru
  handlowego bez „FN” pod swoją etykietą („Numer rejestru handlowego:
  30799v”) są rozpoznawane.** Oba stały odręcznie na zeskanowanym
  formularzu przetargowym i pozostawały czytelne, mimo że rozpoznawanie
  tekstu odczytało je poprawnie.
- **Strony PDF w poprzek były po zaciemnieniu bez powodu zamieniane na
  obraz.** Sprawdzenie nienaruszoności porównywało oryginał i wynik w
  obróconym widoku, ale liczyło swoje strefy zaciemnienia bez obrotu –
  na stronie z zapisem obrotu własne zaciemnienie leżało przez to obok
  swojej strefy i liczyło się jako uszkodzenie. Takie strony zachowują
  teraz swoją warstwę tekstu i grafikę wektorową.
- **Także zwykłe strony były czasem bez potrzeby zamieniane na obraz**,
  gdy tekst za zastępnikiem przesuwał się o jeden punkt – dozwolone, ale
  porównanie obrazu było dokładniejsze niż jego własna tolerancja.
  Porównuje teraz w połówkach punktu i trafia przez to swoją tolerancję
  dokładnie: do dwóch punktów przesunięcia nic nie reaguje, powyżej
  wszystko.
- **Dane w osadzonych obiektach formularza pozostawały.** Niektóre
  szablony odkładają nagłówek lub stopkę listu jako osobny formularz,
  który strona tylko osadza. Trafienie w nim było wprawdzie planowane i
  liczone jako usunięte, ale nigdy nie zapisywane – tekst stał tam dalej,
  a chwytała go tylko rasteryzacja całej strony. Teraz sam formularz
  jest przepisywany; formularz leżący na kilku stronach – tylko raz.
- **Strony PDF były rasteryzowane na obraz, mimo że nic czytelnego nie
  pozostało.** Siedmiostronicową ofertę dotknęło to na sześciu stronach;
  urosła z 73 kB do 3,3 MB i straciła swoje pismo na rzecz odwzorowania.
  Przyczyną były spacje stojące w dokumencie kilkakrotnie pod rząd, ale
  zgłaszane przez czytnik tylko raz: tekst za usuniętą daną przesuwał
  się o jej szerokość w prawo, kontrola znajdywała sąsiednie słowo w
  prostokącie znalezienia i sięgała po rasteryzację. Zachowane resztki
  wierszy stoją teraz znów dokładnie na swoim miejscu; ta sama oferta
  jest oczyszczana bez ani jednej zrasteryzowanej strony (76 kB).
- **Nazwy kluczy i nagłówki faktur liczyły się jako osoby.** W pliku
  dostępowym zastępowana była nazwa zmiennej środowiskowej
  („AWS_ACCESS_KEY_ID”), nie tylko jej wartość; na angielskiej fakturze
  nagłówek „Bill to” padał jako imię. Identyfikator wielkimi literami z
  podkreśleniami nigdy nie jest nazwiskiem, a słowo w wierszu będącym w
  całości etykietą pola też nie – odbiorca pod spodem jest nadal
  znajdywany.
- **Wyszukiwanie w oknie poprawek zacinało się przy dużych stronach
  PDF.** Każda litera w polu wyszukiwania kazała rasteryzować stronę na
  nowo, mimo że zmieniało się tylko wyróżnienie. Wyrenderowany obraz
  strony pozostaje teraz, dopóki strona, powiększenie i widok są takie
  same – także oryginał w lupie porównawczej; przewijanie, powiększanie
  i nowy stan pliku rysują jak dotychczas na nowo.
- **Numery pozycji w ofertach liczyły się jako adres IP lub numer
  telefonu.** Wiersz artykułu jak „1.3.3.4 … 5-portowy switch Gigabit”
  robił z numeru strukturalnego adres sieciowy, bo „Port” liczył się
  jako otoczenie techniczne – teraz liczy się tylko jako samodzielna
  dana („Port 80”), nie jako część słowa. A „1.3.3.6 216879” (numer
  pozycji plus numer artykułu) nie jest już zaciemniane jako numer
  telefonu. Prawdziwe adresy IP i numery telefonu w takich listach
  pozostają rozpoznawane.
- **Wiersze artykułów w ofertach liczyły się jako kod pocztowy z
  miejscowością.** „35252 DIETZEL SALR” (numer artykułu wraz z
  producentem) i „1000 AWG” (ilość wraz z przekrojem przewodu) były w
  numerowanych wierszach pozycji zaciemniane jako adres, bo słowo wielkimi
  literami za liczbą liczyło się jako nazwa miejscowości wielkimi
  literami. W listach pozycji już się to nie liczy; „1080 WIEN” w bloku
  adresu i miejscowości pisane małą literą pozostają rozpoznawane
  wszędzie.
- **Dodatkowe rozpoznawanie nazwisk zaciemniało w ofertach wiersze ról
  i nagłówki kolumn.** „Stawka godzinowa Monter + E-Helfer” liczyła się
  49 razy jako osoba, nagłówek kolumny „Poz. Oznaczenie Ilość JM” 19 razy
  jako miejscowość – 19-stronicowe zlecenie stawało się przez to
  nieczytelne. Takie trafienia w wierszach pozycji padają teraz, gdy same
  niosą znaki, których nazwisko nie ma (plus, ukośnik, cyfra, skrót) –
  także wtedy, gdy wiersz kończy się kwotą („Alternatywnie Rynek … - PV/LS
  zasilanie AC 1 290,00”). Nazwiska w spisach i listach – do czego ten
  poziom służy – pozostają nienaruszone.
- **„Der Kunde” robiło w warunkach handlowych z każdego „Kunde”
  nazwisko.** Jeśli dodatkowe rozpoznawanie nazwisk brało rodzajnik do
  trafienia, liczyło się to jako nazwisko dwuczłonowe i chroniło
  wszystkie 35 dalszych miejsc tego samego słowa. Teraz rodzajnik jest
  odejmowany, a „der Kunde” pada tak samo jak już wcześniej „des
  Kunden”.
- **Etykiety liczyły się jako wartość.** „E-Mail” było siedem razy
  zaciemniane jako adres e-mail, „Telefonnummer” i „Faxnummer” jako
  numer telefonu. Adres bez @ i numer telefonu bez cyfr już się nie
  liczą.
- **Skróty kolumn z jednej litery („L: 154,50”, „S: 0,00”) liczyły się
  jako nazwisko** – 25 razy w ofercie fotowoltaicznej. Pojedyncza litera
  nie jest ani nazwiskiem, ani miejscowością.
- **Strony PDF były zbyt często zamieniane na obraz.** Dwie przyczyny,
  obie znalezione na prawdziwych ofertach: jeśli PDF ustawia każdy glif
  jako osobne polecenie i tkwi pod tym glif spacji bez znaku tekstowego,
  przyporządkowanie przesuwało się od tego miejsca o jeden – z usuniętej
  wartości pozostawała ostatnia litera („ŠkodaTopCar**d**”), a kontrola
  słusznie rasteryzowała stronę. A słowo rozdzielone na końcu wiersza
  („Datenschutz-”) liczyło się z powodu znacznika łącznika biblioteki
  odczytu jako przesunięte. Oba naprawione: oferta pojazdu spadła z 4
  zrasteryzowanych stron do 0, 19-stronicowe zlecenie z 7 do 0 – pismo
  pozostaje pismem, plik pozostaje mały.
- **Naprawiono dwa dalsze powody rasteryzacji:** jeśli dokument sam niesie
  czcionkę o nazwie „F1”, zastępniki nad obrazami były ustawiane jego
  czcionką i były nieczytelne – teraz własna czcionka etykietowania
  dostaje wolną nazwę. A jeśli bibliotece odczytu brakuje spacji w
  środku długiego polecenia tekstowego, miejsce jest teraz dowodzone
  także przy czcionkach wielobajtowych (ten sam kod, ten sam znak)
  zamiast trafiać na koniec – wcześniej pozostawała przy tym litera
  usuniętej wartości, a reszta tekstu przesuwała się widocznie w bok.
  Do tego dwa ostatnie przypadki: polecenie z kilkudziesięciu glifów
  spacji odbiegało przyporządkowaniu (nazwisko za nim pozostawało), a
  duży nagłówek z szerokością przesunięcia nie znajdował swojego
  pierwszego znaku (nazwa firmy pozostawała). **Z dziewięciu prawdziwych
  ofert nie jest teraz rasteryzowana ani jedna strona** – wcześniej było
  to 30 z 90.
- **Przy rasteryzacji obrazy znikały pod czarnym blokiem.** Jeśli strona
  musi być zamieniona na obraz, jest renderowana z oryginału – a ten nie
  zna oczyszczania obrazów. Dotychczas przez to padała *każda* powierzchnia
  obrazu strony pod pas, także nietknięta. Na ofercie adres i dwa logo
  certyfikatów tkwiły w tym samym obrazie nagłówka; pas zabierał logo
  razem. Teraz wstawiany jest już oczyszczony obraz: adres w nim jest
  zaciemniony, reszta pozostaje widoczna. Usunięty obraz pozostawia biały
  papier zamiast czarnego pola.

- **Oczyszczone skany stawały się wielokrotnie większe niż oryginał.**
  Każdy obraz, w którym coś zaciemniono, wracał do pliku jako
  nieskompresowany obraz surowy – przy 24-stronicowym skanie plik urósł
  przez to z 11,8 do 52,9 MB. Obrazy zachowują teraz rodzaj, w jakim
  były: zdjęcie pozostaje zdjęciem, skan faksu pozostaje czarno-biały,
  bezbarwny obraz nie jest odkładany jako kolorowy. Ten sam plik ma
  teraz 15,6 MB, bez widocznej różnicy.

- **Zeskanowane pliki PDF z urządzeń biurowych wracały jako wzór
  paskowy.** Takie skany kładą pismo jako ostrą warstwę czarno-białą nad
  zgrubny obraz kolorowy – Canon, Xerox i Kofax budują tak swoje pliki.
  Przy zaciemnianiu w obrazie ta warstwa była błędnie zapisywana z
  powrotem; wynik był nieczytelny. Przy sześciostronicowej ofercie
  dotyczyło to dziewięciu z szesnastu obrazów. Jest teraz obsługiwana
  poprawnie, w swoim własnym kolorze, a zaciemnione miejsca w niej
  naprawdę zniknęły.

- **„Usuń wszystkie obrazy” zabierało zeskanowanej stronie jej tekst.**
  Warstwa pisma takiego skanu jest technicznie obrazem – była razem
  usuwana lub rozmywana, a pozostawała pusta kartka. Pozostaje teraz;
  logo, pieczątki i podpisy nadal ustępują.

- **Sprawdzenie uszkodzonych stron PDF nie rasteryzuje już z powodu
  drobnego przesunięcia.** Fragment tekstu na nowo zakotwiczony przy
  oczyszczaniu może przesunąć się o do dwóch punktów; porównanie obrazu
  mimo to liczyło to jako uszkodzenie i budowało stronę na nowo jako
  odwzorowanie – przy tym ginęła grafika wektorowa jak linie tabel, a nad
  miejscami znalezienia leżał pas zamiast zastępnika. Porównanie
  dopuszcza teraz to samo małe przesunięcie co sprawdzenie słów;
  prawdziwe uszkodzenia nadal się zauważa.

- **Przywracanie wielu wartości pod rząd nie zawodzi już na Windows na
  „Odmowie dostępu”.** Kto w pliku biurowym przywracał wiele wierszy
  panelu krótko po sobie, mógł natrafić na krótkotrwałą blokadę pliku
  przez skaner antywirusowy; wymiana odczekuje teraz krótko takie
  blokady.

- **Windowsowa droga przekazywania poleceń kończyła sprawdzającego
  zamiast sprawdzać.** Sprawdzenie żywotności nasłuchującej instancji
  wysyłało na Windows przypadkowo prawdziwe Ctrl+C do własnej grupy
  konsoli; teraz pyta system bez sygnału.

- **Wieloczłonowe etykiety pól nie działały, za to działały ich
  fragmenty.** „Date of birth”, „Bank account”, „Cuenta bancaria” i
  „Numero de cliente” stały na liście etykiet, ale były tam rozłożone na
  pojedyncze słowa i przez to nigdy nie trafiały; pozostawały fragmenty
  słów jak „de” i „of”, które od tego czasu liczyły się jako etykieta –
  „de” jest jednak składnikiem nazwiska („Anna de Vries”). Oba
  naprawione: zwroty działają teraz jako całość, fragmenty zniknęły.

- **Niemieckie formuły pożegnalne z „ß” były mimo wpisu traktowane jako
  nazwisko osobowe.** Pod „Herzliche Grüße” lub „Mit freundlichen
  Grüßen” stał w wyniku zastępnik, mimo że oba zwroty od zawsze stoją na
  liście przeciwnej. Przyczyną była pisownia, która przy porównaniu
  nigdy nie docierała; dotyczyło to ośmiu wpisów w pięciu listach.
  Działają teraz wszystkie.

- **„John Staff” pozostawało niezastąpione.** Nazwisko będące
  jednocześnie angielskim nagłówkiem kolumny było odrzucane razem przez
  filtr etykiet. Nagłówek pozostaje nadal nienaruszony, nazwisko pod nim
  jest znów zastępowane.

- **Wartości z opisanych pól formularza pozostają chronione w poziomie
  SI.** Lokalny arbiter poziomu SI dostawał dotychczas do oceny też
  trafienia, których znaczenie już potwierdza etykieta pola („Data
  urodzenia:” nad wartością) – i mógł je odrzucić. Takie strukturalnie
  udokumentowane wartości nie są mu już przedkładane. Plik
  przyporządkowania nazywa teraz przy każdym zastąpieniu dodatkowo drogę
  rozpoznania („dowód”).

- **Strona PDF, której zachowany tekst poniósł szkodę przy oczyszczaniu,
  jest teraz rozpoznawana i przebudowywana na nowo jako odwzorowanie
  oryginału.** Przy niektórych czcionkach generatorów zachowane miejsca
  tekstu mogły po oczyszczeniu pojawiać się jako czarne bloki lub słowa
  zbijały się razem, mimo że wszystkie dane do usunięcia zostały
  poprawnie usunięte. Maskuro porównuje teraz wynik słowo po słowie i
  piksel po pikselu z oryginałem; uszkodzona strona jest zastępowana
  swoim czystym odwzorowaniem — z pasami zaciemniającymi nad miejscami
  znalezienia, zaciemnionymi obszarami obrazu i przeszukiwalnym tekstem.
  Strona pozostaje czytelna, usunięcie niezawodne.

### Zmienione

- **W przetłumaczonych interfejsach każdy termin fachowy nazywa się
  teraz wszędzie tak samo.** Dla jednego i tego samego niemieckiego
  słowa stały w zależności od okna dwa lub trzy tłumaczenia obok siebie:
  dziennik sprawdzeń nazywał się po norwesku częściowo „Revisjonslogg”,
  częściowo „Kontrollogg”, wersja darmowa częściowo „Gratisnivå”,
  częściowo „Gratisversjon” – i podobnie w tuzinie dalszych języków. Kto
  szukał ustawienia, znajdował je w następnym oknie pod inną nazwą.
  Ujednolicono na słowo, które interfejs i tak prowadzi najczęściej.

  Przy tym wyszły na jaw miejsca, gdzie jedno słowo stało za dwie
  **różne** rzeczy: francuski, grecki i koreański używały dla
  „zaciemnij” i „zamaskuj” tego samego wyrażenia – więc akurat tam,
  gdzie program wyjaśnia różnicę („Zaciemnianie usuwa bez zastąpienia,
  maskowanie zachowuje formę”). Oba są teraz rozdzielone. Dla
  szwedzkiego ta decyzja jeszcze czeka: tam zaciemnianie nazywa się
  „maskera” – to samo słowo co maskowanie.

- **Pytanie o rodzaj użytkowania przy pierwszym uruchomieniu
  odpadło.** Krótko po starcie pojawiało się okno („Prywatnie czy w
  firmie?”), a w ustawieniach stał do tego wiersz. Obu już nie ma –
  bezpowrotnie. Dana, od której nic nie zależy, podaje błędnie, kto
  chce niewłaściwej licencji, a kto jest uczciwy, nie potrzebuje jej;
  kosztowała każdego jedno kliknięcie w momencie, w którym nikt nie
  myśli o rodzajach licencji. Która licencja jest właściwa, stoi tam,
  gdzie się o niej decyduje: na stronie z cenami, w kasie i w pomocy.
  Firmy wdrażające Maskuro centralnie nadal ustalają rodzaj użytkowania
  przez plik wytycznych.

- **Wskazówki o rodzaju licencji nazywają przypadek, o który chodzi.**
  Licencja prywatna obowiązuje wyłącznie dla użytku prywatnego; każda
  praca zawodowa lub gospodarcza wymaga licencji firmowej – także jako
  jednoosobowa działalność bez pracowników. Stało tak w warunkach
  licencji, ale ani w programie, ani w pomocy: tam była mowa zawsze
  tylko o domenie firmowej, a ta akurat tego przypadku nie obejmuje:
  komputer osoby samozatrudnionej nie należy do żadnej domeny.
  Wskazówka przy wczytywaniu licencji prywatnej mówi to teraz, podobnie
  rozdział licencyjny instrukcji i często zadawane pytania, które
  dostały do tego własny wpis. Nadal nic nie jest blokowane.

- **Jeszcze niedostarczone drogi leżą teraz razem.** Ustawienia dostały
  stronę „Deweloper”; tam stoją maksymalne rozpoznawanie (SI) wraz z
  jego kontrsprawdzaniem, katalog list słów i obserwacja folderu.
  Wszystkie trzy są zbudowane, ale nie wypróbowane w praktyce – są
  dlatego widoczne tylko z licencją deweloperską, i to wszędzie
  jednocześnie: strona, wpisy menu i skutek w przebiegu zależą od tej
  samej decyzji. Bez tej licencji wcześniej włączony poziom SI
  pozostaje bezskuteczny; jego ustawienie nie jest usuwane i obowiązuje
  znów, gdy tylko droga zostanie dostarczona.

### Ulepszone

- **„Co jest szukane” pokazuje trzy dalsze listy z rozpoznawania
  nazwisk.** Formy grzecznościowe, po których następujące słowo jest
  czytane jako nazwisko; tytuły i role, po których dalej **nie** ma
  nazwiska („Pan Burmistrz Huber”); oraz osiemdziesiąt wielojęzycznych
  etykiet, przy których rozpoznawane są sygnatury akt, numery procesu i
  sprawy. Wszystkie trzy działały zawsze, tylko nie były widoczne w
  przeglądzie.

- **„Co jest szukane” pokazuje dwie dotychczas brakujące listy słów.**
  Formy grzecznościowe i tytuły czyniące poprzedzające słowo nazwiskiem
  („Pan”, „Pani”, „Dr.”), oraz skróty organizacji normalizacyjnych,
  przy których Maskuro odróżnia odsyłacz normowy jak „ÖNORM B 2110” od
  osoby. Oba wpływają na rozpoznawanie od zawsze, ale nie stały w
  przeglądzie.

- **Listy pozycji, spisy treści, wyliczenia wyposażenia i odsyłacze
  normowe pozostają czytelne.** Rozpoznawanie widzi teraz budowę
  wiersza: zgadnięte nazwisko w wierszu strukturalnym („1.3.1 Kabel
  ziemny energetyczny 1kV”), wierszu spisu z kropkami wiodącymi,
  wyliczeniu („- ładowanie bezprzewodowe z pierścieniem magnetycznym”),
  nad wierszem ilości/ceny, w nagłówku kolumny lub za „za pomocą” jest
  pojęciem rzeczowym i nie jest już zastępowane. Prawdziwe nazwiska
  pozostają chronione – przez formę grzecznościową, etykietę pola i
  dowód w innym miejscu dokumentu; na korpusie pomiarowym żadna dana nie
  straciła ochrony. W korpusie biznesowym fałszywe alarmy spadają przez
  to z 25 do 6.

- **Nagłówki, etykiety formularzy i formuły pożegnalne rzadziej są brane
  za nazwiska – po niemiecku i angielsku.** Listy słów, którymi Maskuro
  odróżnia rzeczowniki pospolite od nazwisk osobowych, wyraźnie urosły:
  etykiety z faktur, formularzy i poczty urzędowej („Sygnatura akt”,
  „Tytuł płatności”, „Miejsce powstania kosztów”, „Sort code”,
  „Subtotal”), nagłówki sekcji aplikacji i raportów („PRZEBIEG KARIERY”,
  „KWALIFIKACJE”, „SUMMARY”, „REFERENCES”), niemieckie i angielskie
  rodzaje pism („Potwierdzenie zlecenia”, „Protokół”, „Timesheet”,
  „Agreement”) oraz formy rozkazujące z instrukcji („Wyślij…”,
  „Select…”). Strona angielska była przy tym dotychczas zauważalnie
  słabo obsadzona.

- **Opisane pola zdradzają teraz, co w nich stoi, także gdy etykieta
  jest złożona.** „Adres dostawy”, „Adres faktury”, „Osoba prowadząca
  sprawę”, „Posiadacz konta”, „Contact person” i „Billing address”
  przyporządkowują teraz wartość obok lub pod sobą do tego samego
  rodzaju co proste „Adres” czy „Nazwisko” – w wypełnionym formularzu z
  polami to różnica między znalezione a przeoczone.

- **W oknie poprawek kółko myszy przewija dalej na brzegu strony.** Kto
  przewija na końcu strony dalej, ląduje na górze następnej; kto
  przewija na początku wstecz, na dole poprzedniej – dokument da się
  przez to przewinąć od początku do końca, bez dotykania przycisków
  strony. Klawiatura (Strona↑/Strona↓) potrafiła to już; krótka pauza
  między dwiema zmianami stron zapobiega, żeby dobieg gładzika przeniósł
  przez połowę dokumentu.

- **Miniatury stron w oknie poprawek siedzą wyśrodkowane w panelu.**
  Dotychczas przylegały do lewej krawędzi, a przy rozciąganiu szerzej
  rósł tylko pusty margines po prawej.

- **Pasek symboli okna poprawek pokazuje swoje grupy.** Kreski
  rozdzielające mają teraz przestrzeń i kolor, „Szukaj” i „Zastosuj do
  wszystkich stron” stoją jako osobne grupy obok narzędzi, a „Zastosuj”
  pojawia się już tylko przy rodzajach dokumentów, w których może coś
  zdziałać. Każdy wpis na pasku i w menu nosi teraz obraz: „Wiersze
  tekstu” i lupa porównawcza dostały własne symbole (lupa dzieliła
  dotychczas swój z „Przed/po”), do tego powiększenie, cała strona,
  szerokość strony, obrót, przewijanie i skróty klawiszowe. „Otwórz
  programem systemowym” stoi teraz też na pasku obok drukowania – droga
  od gotowego wyniku do przyzwyczajonego programu to jedno kliknięcie,
  nie przejście przez menu.

- **Przy oczyszczaniu schowka znów stoi obok, że trzeba sprawdzić.** W
  ustawieniach wskazówka stoi trwale obok przełącznika: Maskuro może
  przeoczyć dane osobowe lub błędnie potraktować dane, wklejony tekst
  należy przed przekazaniem sprawdzić. Przy włączaniu nazywa ją
  dodatkowo komunikat, a jest odnotowywana w obszarze wyjścia – także
  wtedy, gdy w obszarze powiadomień nie działa żadna ikona. Przy każdym
  pojedynczym kopiowaniu celowo się nie pojawia: wskazówka pojawiająca
  się pięćdziesiąt razy dziennie po trzecim razie nie byłaby już
  czytana.

## 0.10.36-beta.1 – 20 sierpnia 2026

### Ulepszone

- **Techniczne dokumenty biznesowe nie są już rozrywane zaciemnieniami.**
  Cztery hamulce rozpoznawania, wyprowadzone z jedenastu prawdziwych ofert
  i zleceń: numery strukturalne („1.3.1.1") nie liczą się już jako
  adresy IP, odsyłacze normowe („ÖNORM EN 62446") i kody identyfikacyjne
  już nie jako kod pocztowy czy numer telefonu, a słowa ról za
  rodzajnikami („klient", „zamawiającego") już nie jako nazwiska – w
  warunkach handlowych prawdziwej oferty wszystkie 46 słów ról jest
  dzięki temu znów czytelnych zamiast zaciemnionych. Adresy z
  oznaczeniem kraju („A 3390 Melk", „D-94032 Passau") są teraz usuwane w
  całości, zamiast pozostawiać kod pocztowy jako sierotę.

- **Listy słów są teraz w pełni wglądowe.** Pod „Pomoc → Listy słów …”
  można przeglądać lokalnie używane listy rozpoznawania i kontrsprawdzania
  wraz z językiem, celem, źródłem i zawartością. Należą do nich także
  listy wordfreq, medyczne, osobiste i zarządzane centralnie, jak
  również zasoby dla wymyślonych wartości zastępczych. Podręcznik opisuje
  katalog w osobnym rozdziale.

- **Gotowe wiersze plików pokazują użyty język rozpoznawania.** Za
  słowem „gotowe” stoi teraz np. „niemiecki” lub „angielski”, żeby
  niepasujący automatyczny wybór języka od razu było widać. Jeśli musiał
  wskoczyć inny zainstalowany język, strzałka pokazuje oba języki.

- **Nowa lupa porównawcza pokazuje przy czytaniu od razu pasujące
  miejsce w oryginale.** Jej powiększony wycinek oryginału podąża za
  kursorem myszy nad wciąż edytowalnym wynikiem; przy tekście podąża za
  akapitem. Lupę można używać na krawędzi okna lub wyciągnąć jako własne,
  maksymalizowalne okno. Jej powiększenie da się ustawić bezpośrednio
  między 50 a 300 procent i jest zapamiętywane tak samo jak włączenie.
  „Resetuj” przywraca też zmaksymalizowaną lub niekorzystnie zadokowaną
  lupę z powrotem po lewej do obsługiwalnego rozmiaru. Zastąpione
  wartości oryginału są w lupie podświetlone na żółto, żeby dotknięte
  słowa od razu rzucały się w oczy przy czytaniu. Raz aktywowana, otwiera
  się przy przyszłych odpowiednich dokumentach ponownie – także po
  ponownym uruchomieniu programu. Dotychczasowy przełącznik przed/po
  pozostaje zachowany w menu widoku. Podręcznik opisuje ją w osobnym
  rozdziale.

- **Dowody open source i modeli są teraz dokładne co do wydania.**
  Budowa pakietu tworzy czytelną dla maszyn listę komponentów wraz z
  sumami skrótu dołączonych tekstów licencyjnych. Źródła MPL,
  pochodzenie modeli, stałe rewizje, zmiany i SHA-256 są dokumentowane
  osobno; doładowane modele otrzymują swój dowód pochodzenia
  bezpośrednio w folderze modelu. Ruchome listy odniesień Tesseract i
  spaCy zostały na stałe przypięte. Artefakty sprzedażowe pozostają
  zablokowane, dopóki wszystkie źródła i załączniki modeli nie zostaną
  opublikowane i sprawdzone.

- **Lokalny zbiór danych wordfreq jest w pełni udokumentowany
  licencyjnie.** Budowa pakietu sprawdza wersję 3.1.1, 39 niezmienionych
  małych list łącznie z CJK i mapę znaków chińskich pod względem
  liczby, rozmiaru i sumy kontrolnej manifestu. Informacja o kodzie
  Apache-2.0, pełna licencja CC-BY-SA-4.0, przypisanie autorstwa,
  źródła danych oraz pominięte duże, Jieba i nieobsługiwane listy są
  udokumentowane w pakiecie.

- **Częste słowa zdaniowe są rzadziej mylnie zaciemniane.** Lokalny
  słownik częstości służy jako dodatkowa kontrsprawdzanie, gdy
  rozpoznawanie nazwisk uzna czasownik, zaimek, rodzajnik lub przyimek za
  osobę. Słownik nigdy nie decyduje sam: rzeczowniki, nazwiska
  wieloczłonowe oraz nazwiska w polach, listach i po formach
  grzecznościowych pozostają chronione. Chiński, japoński i koreański
  używają wyłącznie dokładnych granic tokenów swoich już istniejących
  modeli językowych; dla nieistniejących języków nie stosuje się rzekomo
  podobnego języka słownikowego. Do tego żaden tekst dokumentu nie jest
  przesyłany do internetu.

- **Techniczne terminy produktowe i wyposażeniowe rzadziej są brane za
  nazwiska lub miejscowości.** Lokalna kontrsprawdzanie łączy teraz
  częstość, część mowy, techniczne tworzenie słów i pola tematyczne.
  Dzięki temu pozostają w dokumencie np. „Travel-Assistent",
  „Family-Bonus", „WLTP-Wert", „Easy-Start" i złożone terminy numerów,
  uchwytów czy hamulców. Elementy angielskie są sprawdzane lokalnie
  także w niemieckim tekście fachowym; prawdziwe nazwy własne, formy
  grzecznościowe oraz pola osobowe i miejscowości zachowują pierwszeństwo.
  Ponadto „2-letnia gwarancja producenta” nie liczy się już jako wiek
  życia.

- **Prawa licencyjne Qt/PySide są teraz w pełni prześledzalne.** Pakiet
  programu zawiera dodatkowo pełny tekst GPL-3.0, dokładne wersje Qt,
  ofertę kodu źródłowego oraz niemiecko/angielską instrukcję wymiany
  bibliotek dynamicznych łącznie z lokalnym ponownym podpisaniem na
  macOS. Budowa sprzedażowa jest blokowana, dopóki dokładne archiwa
  źródłowe dostarczonej wersji nie są dostępne na własnej stronie kodu
  źródłowego.

- **Licencja i stan aktualizacji mówią teraz dla każdego poziomu
  jednoznacznie, co obowiązuje.** W oknie licencji i przy ustawieniach
  aktualizacji stoi, czy aktualizacje są zawarte, do jakiego dnia
  sięgają i czy bieżąca wersja pozostaje trwale użytkowalna. Licencje
  prywatne po dacie granicznej nie instalują już później wydanej wersji;
  także świeżo pobrany instalator rozpoznaje po swojej na stałe
  wbudowanej dacie wydania, czy wprowadzony klucz go obejmuje. Ostatnia
  objęta wersja prywatna pozostaje trwale użytkowalna. Jeśli natomiast
  kończy się abonament firmowy, kończy się użytkowanie i aktualizacje;
  okres testowy i wersja darmowa nie otwierają się jako obejście.

- **Prywatne licencje dożywotnie znajdują teraz właściwy stan programu
  także po ponownej instalacji.** Podpisany katalog wersji prowadzi
  wszystkie stabilne wydania i ich pakiety. Jeśli ostatni objęty zakupem
  instalator nie jest już dostępny, wolno zamiast tego automatycznie
  użyć dokładnie najbliższej wyższej dostępnej wersji stabilnej – nigdy
  bety ani nightly. Przy zbyt nowej instalacji klient może zainstalować
  dopuszczalny stan lub przejść na stronę zakupu po nowy okres
  aktualizacji; cofnięcie nie odbywa się po cichu. Dotyczy to także
  zarządzanych instalacji MSI.

- **Automatyczne zaciemnianie twarzy jest teraz jednoznacznie opisane.**
  Pomoc programu i tekst o ochronie danych nazywają funkcję
  „Rozpoznawanie i zaciemnianie obszarów twarzy” i odgraniczają ją od
  identyfikacji, ponownego rozpoznawania, porównania twarzy, wzorców
  biometrycznych oraz baz danych osób czy twarzy. Wskazują ponadto
  wyraźnie, że w pełni lokalne rozpoznawanie może przeoczyć obszary lub
  błędnie je oznaczyć i wynik musi dlatego zostać sprawdzony wzrokowo.
  Także przy pojedynczo oczyszczonym pliku obrazu raport wyniku
  wymienia teraz rozpoznane i spikselizowane obszary twarzy; brakujące
  rozpoznawanie tekstu nie jest przy tym już błędnie opisywane jako
  całkowicie niezmieniony plik.

## 0.10.36-alpha.20260820 – 20 sierpnia 2026

### Naprawione

- **Zanonimizowane dane można teraz w pełni odzyskać niezależnie od
  kolejności.** Wcześniejsze przywracanie szukało wartości poprzez widoczne
  kotwice tekstowe. W gęstych tabelach, bezpośrednio sąsiadujących
  zastępnikach i niewidocznych schowkach Office/poczty tych kotwic
  brakowało; czasem pojęcie stawało się odzyskiwalne dopiero po tym, jak
  inny jawny tekst przypadkowo utworzył nową kotwicę. Teraz wynik i
  oryginał są porównywane dla każdego rzeczywistego nośnika formatu z
  pełnym przyporządkowaniem, a zapisywane są tylko obsadzone miejsca
  wybranej wartości.

- **Nazwiska, adresy e-mail, numery i własne pojęcia sprawdzające
  pozostają jednoznacznie obsługiwalne nawet przy nakładającym się
  rozpoznawaniu.** Jeśli ta sama jawna wartość jest przypisana do dwóch
  rodzajów, decyduje zastępnik faktycznie stojący w miejscu znalezienia
  razem z klikniętym wierszem paska bocznego. Nieobsadzona para
  wartość/zastępnik pozostaje nadal bezpiecznie zablokowana.

- **Przypadki szczególne poczty nie pozostawiają już ukrytych
  zastępników.** Dotyczy to tematów kodowanych w MIME, załączników
  tekstowych i nazwisk rozdzielonych znacznikami HTML w plikach EML i MSG.
  UTF-8-HTML bez własnego oznaczenia zestawu znaków nie jest już ponadto
  w plikach Outlook przekodowywane na mojibake przy każdym kroku
  edycji; starsze, już tak zapisane wyniki pozostają odzyskiwalne.

### Ulepszone

- **Nowa macierz zwolnień obsługuje każdy anonimowy wiersz paska bocznego
  osobno i celowo wstecz.** Sprawdza wszystkie 14 formatów tekstowych,
  biurowych, internetowych i pocztowych oraz PDF, a następnie także
  formuły, atrybuty, relacje, komentarze, nagłówki poczty, załączniki i
  wewnętrzne schowki wewnętrzne. Pełny przebieg na macOS obejmuje teraz
  149/149 zielonych skryptów sprawdzających.

## 0.10.35-alpha.20260820 – 20 sierpnia 2026

### Ulepszone

- **Pomiary językowe porównują teraz naprawdę to samo z tym samym.**
  Regularny korpus pomiarowy zawiera te same 14 przypadków dokumentów z
  tymi samymi siedmioma zadaniami tekstowymi i czterema zadaniami
  obrazowymi po niemiecku i angielsku. Pełny przebieg powtarza dokładnie
  tę macierz dla wszystkich dwunastu dostępnych języków korpusu.
  Formularze, tabele, czaty i inne jeszcze nie w pełni przetłumaczone
  próbki strukturalne pozostają, ale są wykazywane osobno i nie są już
  mieszane z kwotami językowymi.

- **Pełny przebieg zapisuje teraz dla każdego języka własny raport
  pomiarowy.** Bez przełącznika języka celowo sprawdzane są niemiecki i
  angielski; `--alle-sprachen` żąda pełnego dwunastojęzycznego korpusu i
  przerywa przed pierwszym dokumentem, jeśli brakuje języka lub
  przypadku. Wyniki o tej samej nazwie leżą w osobnych folderach
  językowych. Raport zbiorczy podaje obok ważonego wskaźnika trafień
  także nieważoną wartość średnią wskaźników językowych.

- **Otwarte porównanie językowe pokazuje teraz też swoją rzeczywistą
  granicę.** W regularnym przebiegu z rozpoznawaniem tekstu niemiecki i
  angielski usuwają 218/218 znanych danych bez fałszywego alarmu. Pełny
  test z rozpoznawaniem tekstu i poziomem Wysokim usuwa 1255/1308 danych
  przy 17 fałszywych alarmach; jedenaście języków osiąga 100 procent,
  hindi 51 procent. Wcześniejsze pełne wskaźniki opierały się na
  nierównych zbiorach dokumentów i wartości docelowych i nie są
  porównywalne z nową macierzą.

## 0.10.34-alpha.20260819 – 19 sierpnia 2026

### Naprawione

- **Wielokrotnie występujące nazwiska pozostają po pojedynczym
  przywróceniu osiągalne na pasku bocznym.** Dotychczas cały wiersz
  nazwiska znikał już po pierwszym przywróconym miejscu `[NAZWISKO]`.
  Kolejne miejsca tego samego nazwiska pozostawały przez to jako
  zastępniki i były czasowo nawet zablokowane, dopóki inne nazwiska nie
  zostały przywrócone. Teraz wiersz znika dopiero po ostatnim miejscu;
  już przywrócony jawny tekst mimo to nie jest ponownie automatycznie
  anonimizowany. Dotyczy to również częściowo udanego zbiorowego
  przywracania i narzędzia ramki w plikach PDF.

- **„Cofnij zastąpienie” działa też z podglądu biurowego.** Widoczna
  strona jest tam tylko ulotnym podglądem PDF; teraz poprawnie zmieniany
  jest dokument Word, arkusz kalkulacyjny lub prezentacja pod spodem, a
  następnie odświeżany podgląd.

- **Przywracanie odzyskuje teraz też w pełni ukryte odpowiedniki
  wartości.** W plikach Word, OpenDocument, Excel i PowerPoint te same
  dane mogą dodatkowo znajdować się w formułach, komentarzach,
  wykresach, wartościach pól, tekstach alternatywnych i celach odsyłaczy;
  HTML, EML i MSG prowadzą je ponadto w atrybutach, JSON, nagłówkach
  wiadomości i załącznikach. Dotychczas w zależności od formatu część
  pozostawała jako zastępnik. Teraz każdą oferowaną w obszarze trafień
  daną można przywrócić niezależnie i w dowolnej kolejności. Celowo
  usunięte metadane, historie zmian i nagłówki transportowe pozostają
  ze względów bezpieczeństwa nadal usunięte.

- **Przy odzyskiwaniu z obrazów nie pozostaje już czarna linia
  krawędzi.** Prawa i dolna krawędź ramki były przy kopiowaniu z
  oryginału o jeden piksel za wąsko wyznaczone. Współrzędne odpowiadają
  teraz zaciemnieniu.

### Ulepszone

- **Sprawdzenie zwolnienia przepuszcza teraz każde z 22 obsługiwanych
  rozszerzeń plików przez pełną trasę objazdową.** Bogate w treść pliki
  są oczyszczane, wszystkie oferowane wartości przywracane, a następnie
  dokładnie sprawdzane. Do tego dochodzi rzeczywista obsługa paska
  bocznego, porównania obrazów co do piksela i widoczny render
  LibreOffice wszystkich siedmiu formatów biurowych. Małe testy
  regresyjne pozostają tam, gdzie pokrywają własny przypadek błędu lub
  bezpieczeństwa; wykazany podwójny test HTML i test usuniętego trybu
  czarno-białego odpadły.

- **Pełny korpus pomiarowy tego wydania jest dostępny do ponownego
  pomiaru.** Pakiet zawiera 294 syntetyczne dokumenty w dwunastu
  formatach i dwunastu językach, 2564 znane dane, cztery czytelne dla
  maszyn listy docelowe i instrukcję. Pobieranie na stronie jakości
  używa nazwy pliku zależnej od treści, aby przeglądarki przypadkowo nie
  dostarczyły starszego wydania z pamięci podręcznej.

## 0.10.33-alpha.20260819 – 19 sierpnia 2026

### Nowe

- **Także w plikach obrazów poszczególne miejsca można teraz odzyskać z
  oryginału.** Narzędzie ramki „Przywróć oryginał” kopiuje piksele z tej
  samej pozycji z powrotem z nienaruszonego pliku źródłowego. Droga ta
  pozostaje zablokowana, jeśli źródło brakuje lub ma inne wymiary obrazu;
  dzięki temu żadna treść z przesuniętego miejsca nie może zostać
  wstawiona.

### Ulepszone

- **Ręczne pasy zaciemniające domyślnie zatrzaskują się na liniach
  tekstu.** Przeciągnięcie przez kilka linii tworzy dla każdej linii pas
  o równej wysokości i zostawia wolną przestrzeń między nimi. Dla
  podpisów, grafik i innych przypadków szczególnych „Wolna ramka”
  przełącza z powrotem na samodzielnie wybraną wysokość.

- **Edytor wyjaśnia następny krok bezpośrednio nad dokumentem.** Wskazówka
  zmienia się wraz z rodzajem dokumentu i narzędziem i mówi, czy
  oczekiwane jest kliknięcie słowa, zaznaczenie tekstu czy ramka.
  Dodatkowo narzędzie, kursor myszy i podgląd na żywo pokazują już przed
  puszczeniem przycisku, co się stanie.

### Usunięte

- **Zawodne wyjście czarno-białe zostało usunięte.** W niektórych PDF-ach
  niewidoczne pola tekstowe pozostawały przesunięte względem
  zrasteryzowanej strony; pozorne zmniejszenie pliku nie było warte tego
  ryzyka bezpieczeństwa i wyświetlania. Zwykłe oczyszczanie PDF i celowe
  rasteryzowanie problematycznych stron pozostają zachowane.

## 0.10.32-alpha.20260819 – 19 sierpnia 2026

### Nowe

- **Obserwacja folderu działa teraz naprawdę w tle.** Wejście, wyjście i
  reguły stoją na własnej stronie pod „Ustawieniami”. Uruchamiana i
  zatrzymywana jest przez ikonę Maskuro w pasku zadań lub menu; wpis
  pojawia się tylko z odpowiednio odblokowaną licencją. Okno ustawień
  można potem zamknąć, a okno główne schować do ikony, bez kończenia
  obserwacji.

- **Edytor poprawek ma teraz trwały przełącznik trybu nauki.** Znajduje
  się w obszarze trafień i w menu „Narzędzia”. Gdy jest wyłączony, ani
  przy przywracaniu, ani po ręcznych korektach nie pojawiają się pytania
  o tworzenie własnych reguł. Maskuro zapamiętuje wybór dla wszystkich
  przyszłych otwieranych dokumentów; samo przywracanie działa bez zmian.

### Naprawione

- **Duży model dodatkowy da się znów wczytać.** Publiczny magazyn
  odrzucał ogólną domyślną identyfikację Pythona kodem 403. Pobieranie
  modeli używa teraz tej samej wyznaczonej ścieżki sieciowej Maskuro co
  pozostałe własne usługi; niecałe 596 MB pliku i jego suma kontrolna
  pozostają niezmienione.

- **Zmaksymalizowana lupa porównawcza nie zostaje już przy dokowaniu
  wąskim paskiem u górnej krawędzi.** Przed dokowaniem jej wolny stan
  okna jest normalizowany. Zapisany stan zmaksymalizowany jest przy
  następnym otwarciu również przywracany do zmiennego rozmiaru.

- **Zbiorowe przywracanie w tabelach i innych formatach tekstowych
  odzyskuje teraz naprawdę wszystkie wybrane wartości.** Przy
  zanonimizowanych zastępnikach jak `[EMAIL]` Maskuro zapisywał
  dotychczas wartości kolejno. Gdy tylko pierwsza została zastąpiona,
  numery wszystkich pozostałych miejsc znalezienia przesuwały się do
  przodu, a już obliczony plan wskazywał jeszcze na stare numery. Przez
  to wracała tylko część wyboru. Teraz wszystkie wybrane wartości tego
  samego zastępnika są zapisywane razem i ze stabilnymi numerami miejsc
  znalezienia. Jeśli miejsce staje się jednoznaczne dopiero dzięki innej
  przywróconej wartości, Maskuro sprawdza je w tym samym kroku ponownie
  – kolejność wyboru nie ma już zatem znaczenia.

- **„Cofnij zastąpienie” nie pomija już w plikach PDF wybranych
  wartości.** Jeśli zastępnik stał bardzo blisko za innym słowem lub w
  oryginale przecinek wisiał bezpośrednio przy wartości, sprawdzenie
  położenia mogło błędnie przypisać sąsiednie słowo lub znak
  interpunkcyjny do wartości. Przy wspólnym przywracaniu pozostawały
  wtedy pojedyncze zastępniki i wiersze trafień. Sprawdzenie orientuje
  się teraz na rzeczywistym początku słowa i uwzględnia też odmienny
  obrót strony między oryginałem a wynikiem.

- **Przywrócony tekst PDF zachowuje teraz swój pierwotny rozmiar.**
  Dotychczas jako miara służył już zmniejszony zastępnik; dodatkowo dla
  tekstu oryginalnego obowiązywała także pomyślana dla zastępników
  górna granica 11 punktów. Teraz przejmowane są oryginalny prostokąt i
  oryginalny rozmiar czcionki z pliku źródłowego – zarówno w narzędziu
  ramki, jak i przy przywracaniu z panelu trafień.

### Ulepszone

- **Wskazówka sprawdzenia nazywa teraz jaśniej ryzyko szczątkowe.**
  Wyraźnie mówi, że Maskuro może przeoczyć dane lub błędnie potraktować
  informacje, i wzywa przed każdą publikacją lub przekazaniem do
  pełnego sprawdzenia i w razie potrzeby do ręcznej korekty. Dotyczy to
  także tekstu ze schowka i jest w pełni przeniesione we wszystkich 17
  tłumaczeniach.

- **Dziennik sprawdzeń rusza teraz również wewnątrz swoich wierszy bez
  nazwy użytkownika.** Sam dziennik pozostaje wyłączony, dopóki firma
  celowo go nie aktywuje. Potem bez dodatkowej firmowej wytycznej ani w
  wierszu, ani w nazwie centralnego pliku miesięcznego nie ma nazwy
  użytkownika; służy tam do bezpiecznego rozróżnienia pseudonim, którego
  nie da się odgadnąć, wyprowadzony wyłącznie z losowej lokalnej
  tajemnicy profilu. Okno dialogowe licencji nie zaleca już aktywacji,
  zakłada „Bez dziennika” i wcześniej wskazuje na radę zakładową,
  reprezentację pracowniczą i ochronę danych.

- **Zastępowanie nazywa teraz to, co zastępuje.** Zaznaczone nazwisko
  staje się `[NAZWISKO_3]`, miejscowość `[MIEJSCE_1]`, numer telefonu
  `[TELEFON_2]` – zamiast jak dotychczas wszystko `[POJĘCIE_n]`. Rodzaj
  jest rozpoznawany przy kliknięciu; jeśli nie jest jednoznaczny –
  zwykłe słowo, albo nazwisko *i* miejscowość w jednym wyborze – zostaje
  przy ogólnym pojęciu. Zastępnik, który twierdzi coś o rodzaju, co nie
  jest prawdą, byłby gorszy niż taki, który żadnego nie podaje.

- **Narzędzia w oknie poprawek mają teraz klawisz.** **S** zaciemnia,
  **E** zastępuje, **Z** przywraca oryginał, **V** pikselizuje. W
  widoku tekstu działają natychmiast na zaznaczenie, na podglądzie
  strony wybierają narzędzie. **Litery podążają za językiem**, w którym
  obsługiwany jest program – angielski B/R/O/P, włoski O/S/R/P – bo
  pomoc pamięciowa pomaga tylko we własnym języku. Klawisz stoi przy
  przycisku.
  Kto właśnie pisze w pasku wyszukiwania, dalej pisze litery – tam nie
  działają.

- **Program zgłasza raz dziennie, w jakim stanie działa – bez żadnej
  identyfikacji.** Dzięki temu liczymy, ile instalacji jest używanych i
  jak to się rozkłada na okres testowy, wersję darmową i licencję.
  Wychodzą stan, system operacyjny, wydanie, kanał, kraj, język,
  środowisko i poziom rozpoznawania – **nic o Państwa dokumentach i nic,
  po czym dałby się rozpoznać Państwa komputer**. Dwa zgłoszenia od
  Państwa wyglądają dla nas jak zgłoszenia od dwóch różnych osób;
  pojedynczej ścieżki nie da się z tego prześledzić. Co dokładnie jest
  wysyłane i jak da się to wyłączyć, stoi w tekście o ochronie danych w
  punkcie 5.

- **Strony wciągnięte w poprzek stoją teraz same z siebie właściwie.**
  Kartka, która została zeskanowana krzywo, bez odnotowania tego, jest
  rozpoznawana przez poprawki po biegu tekstu i widok jest prostowany.
  Tam, gdzie się to nie udaje – przy czystym skanie bez czytelnego
  tekstu – dwa nowe wpisy w menu „Widok” obracają ręcznie (Ctrl+Shift+L
  i Ctrl+Shift+R). Obracany jest tylko widok: w pliku nic się przy tym
  nie zmienia, a zaciemnianie trafia nadal dokładnie w miejsce, w które
  się klika.

- **Lokalne wydanie prowadzi teraz swoje licencje w pełni i widocznie.**
  Budowa ustala rzeczywiście dołączone pakiety Pythona, odkłada ich
  teksty licencyjne wraz z przeglądem wersji pod `lizenzen` i przerywa
  przy luce. Także Qt, Tesseract i model twarzy mają swoje potrzebne
  teksty; warunki dla samego Maskuro dołączone są jako umowa licencyjna.

- **Widać teraz, w którym zastępniku stoi kursor.** Kto klika w
  zastępnik, widzi go całego rozświetlonego – wraz z nawiasami i
  numerem. Przycisk „Przywróć wybór” działał już wcześniej przy samym
  kliknięciu; tylko nie było widać, którą pozycję trafia. Rozświetlenie
  pozostaje też wtedy, gdy mysz wędruje do przycisku.

- **Kursor myszy mówi teraz, które narzędzie jest wybrane.** Cztery
  narzędzia dzielą tę samą powierzchnię i ten sam gest; do tej pory
  każde wyglądało tak samo. Celownik oznacza zaciemnianie, zamknięta
  dłoń zastępowanie, otwarta dłoń przywracanie.

- **Spreparowany dokument biurowy odrzuca teraz sam program.** Plik
  Word, Excel lub OpenDocument może nieść instrukcje, które przy
  otwarciu wciągają obcy plik z Państwa komputera do swojego tekstu
  albo doprowadzają do przepełnienia pamięci. Oba przypadki były
  odrzucane już wcześniej – ale przez wbudowaną bibliotekę XML, nie
  przez Maskuro. Teraz decyduje o tym sam program, niezależnie od tego,
  która wersja tej biblioteki znajduje się w pakiecie. Dla zwykłych
  dokumentów nic się nie zmienia.

### Naprawione

- **Panel trafień usuwa teraz zaciemnione zastępniki.** Jeśli np.
  `[NAZWISKO_1]` zostało zaciemnione w oknie poprawek, jego wiersz z
  wartością pozostawał dotychczas po prawej stronie, mimo że w
  dokumencie nie było już takiego miejsca. Wiersz znika teraz wraz z
  ostatnim miejscem znalezienia; jeśli ten sam zastępnik występuje
  jeszcze w innym miejscu, pozostaje zachowany.

- **Przy przywracaniu na obróconej stronie sąsiednie słowo pozostaje
  teraz na miejscu.** Pas zaciemniający celowo wystaje odrobinę poza
  tekst; już ten wąski margines mógł dotychczas zabrać sąsiednie słowo
  jak „w”. Teraz liczy się tylko wyraźne nakładanie, nie dotknięcie na
  brzegu.

- **Drugie zastąpienie w tym samym wierszu zabierało dalszą część
  zdania.** Kto zastępował „Obsługa sprawy Quaxi Blubbo przejmuje” dwa
  razy pod rząd, otrzymywał „Obsługa sprawy [MIEJSCE_1] [MIEJSCE_2]” –
  słowo za nim zniknęło bezpowrotnie, bez żadnego komunikatu. Przyczyną
  był sąsiedni zastępnik: reszta wiersza po pierwszym zastąpieniu
  zaczyna się od spacji, a wyszukiwanie jego miejsca w tekście chwytało
  zamykający nawias sąsiada. Potem wszystko było przesunięte o jeden
  znak. Dotyczyło to każdego wiersza, w którym zastępowano lub
  zaciemniano dwukrotnie – także przy przywracaniu obok.

- **Zastępowanie nie zaciemnia już, gdy zastępnik jest za długi.** Jeśli
  obok słowa nie było miejsca na `[POJĘCIE_2]`, obszar był dotychczas
  zamalowywany na czarno – a przez to nie było już widać, że coś tam
  kiedyś stało, a co dopiero do odzyskania. Teraz zapisywana jest
  krótsza pisownia: `[POJĘ_2]`, `[PO_2]`, w ostateczności `[P_2]`.
  Numer bieżący pozostaje na każdym stopniu – po nim przywracanie
  znajduje ponownie miejsce. Tylko tam, gdzie nawet najkrótsza się nie
  mieści, pozostaje przy pasie.

- **Zastępowanie zostawiało tekst, gdy w tym samym wierszu było już
  zaciemnione.** Kto w oknie poprawek przywrócił nazwisko z oryginału,
  potem zastąpił z niego imię (nie było tam miejsca – powstał pas), a
  następnie zastąpił nazwisko, otrzymywał wstawiony zastępnik, ale
  nazwisko **nie zostało usunięte**. Zauważono to tylko dzięki
  ostrzeżeniu przeglądu. Przyczyną był sam wiersz: po pierwszym
  zaciemnieniu jego reszta zaczyna się od spacji, a wyszukiwanie
  miejsca w tekście nie znajdowało w tym oparcia. Dotyczyło to co
  drugiego zaciemnienia w tym samym wierszu.

- **Włączone rozszerzone rozpoznawanie bez jego modelu jest teraz
  zauważalne.** Znacznik mógł być ustawiony, podczas gdy modelu
  brakowało – ustawienia obowiązują dla każdej instalacji, ale model
  leży obok programu. Oczyszczanie przebiegało wtedy bez tego stopnia,
  bez słowa na ten temat. Teraz znacznik mówi, że modelu brakuje, a
  wynik niesie ostrzeżenie. Raz dokonany wybór pozostaje przy tym
  zapisany: gdy tylko model zostanie wczytany, znów działa.

- **Przy anonimizacji odzyskiwane jest teraz właściwe pojęcie.** Kto
  ręcznie zastąpił kilka pojęć, a potem jedno z nich przywrócił, zawsze
  otrzymywał **pierwsze** – z „Kowalski” robiło się „Nowak”.
  Przyporządkowanie zapamiętywało dla każdego zastępnika tylko jedno
  zastąpienie, a przy anonimizacji wszystkie noszą ten sam zastępnik;
  drugie i każde kolejne pojęcie przy tym odpadało. Teraz każda wartość
  otrzymuje swój własny wiersz – także na liście zastąpień, która
  wcześniej była za krótka.

- **W tabelach można teraz też przywracać.** W pliku CSV lub liście
  personalnej zastępniki stoją bezpośrednio obok siebie, oddzielone
  tylko średnikiem. Do tej pory program nie mógł tam ustalić, która
  wartość stała w którym miejscu, i odmawiał – przy `[NAZWISKO]`
  działało, przy `[DATA_URODZENIA]` i `[TELEFON]` nie. Teraz rozkłada
  wiersz na wszystkich zastępnikach. Jeśli miejsce pozostaje naprawdę
  niejednoznaczne, nadal odmawia: błędnie odtworzona wartość byłaby
  gorsza niż brak informacji.

- **A odmowa jest teraz widoczna.** Stała w stonowanej szarości na dole
  krawędzi okna, a zdanie było tak długie, że zostało obcięte – wyglądało,
  jakby nic się nie działo. Zdania są skrócone, a wiersz świeci przez
  kilka sekund w kolorze ostrzegawczym.

- **Przywrócenie utrzymuje się teraz też po następnej interwencji.** Kto
  przy anonimizacji przywrócił kilka miejsc, a potem zastąpił coś
  innego, zastawał wszystkie przywrócone miejsca ponownie zastąpione i
  musiał zaczynać od nowa. Przyczyną było przyporządkowanie: zachowywało
  wartość, a samoczynne dopasowanie dla jednolitych zastępników
  przywracało ją przy następnym zapisie. Teraz obowiązuje: co Państwo
  przywrócą, pozostaje przywrócone – innych miejsc tej samej wartości to
  nie dotyka.

- **W plikach tekstowych, Word, Excel i e-mail wystarczy teraz naprawdę
  jedno kliknięcie w zastępnik.** Komunikat o tym stał już w poprzednim
  wydaniu, ale przycisk „Przywróć wybór” pozostawał zablokowany, dopóki
  nic nie było dokładnie zaznaczone – nie dochodziło się więc w ogóle do
  ścieżki, która ustawiłaby wybór samodzielnie.

### Naprawione

- **Dziennik sprawdzeń nie zdradza już nazwy pliku.** Prowadzi pliki
  celowo jako wartość skrótu zamiast jawnym tekstem, ponieważ nazwa
  pliku zdradza klienta i przedmiot sporu. Ta wartość skrótu dała się
  jednak potwierdzić przez zgadywanie – ścieżka nie jest liczbą losową.
  Teraz do rachunku wchodzi wartość losowa tej instalacji: liczenie i
  rozróżnianie w dzienniku działa nadal, przeliczenie z zewnątrz już
  nie.

## 0.10.31-alpha.20260819 – 19 sierpnia 2026

### Ulepszone

- **Także w plikach tekstowych i arkuszach zastępnik rozświetla się na
  czerwono przy wskazaniu.** Dotychczas czerwony podgląd był tylko na
  stronie PDF. Teraz oba widoki pokazują to samo: to, co jest czerwone,
  trafia następny ruch – a kliknięcie w to miejsce wystarczy do
  przywrócenia.

- **Kliknięcie w słowo wystarczy – prostokąt ustawia edytor sam.** W
  oknie poprawek trzeba było dotychczas ciągnąć prostokąt nad każdym
  miejscem. Teraz wystarczy kliknięcie: ramka układa się wokół słowa i
  pozostaje uchwytna, można ją więc dalej rozciągać lub przesuwać. Przy
  wskazywaniu myszą słowo świeci już na czerwono, więc widać wcześniej,
  co trafiłoby kliknięcie. Tam, gdzie nie ma słowa, ciągnie się ramkę
  jak dotychczas.

- **Nie trzeba już celować prostokątem dokładnie.** Kto ciągnie prostokąt
  nad zastępnikiem lub zaciemnieniem, ma zawsze na myśli całe miejsce –
  nigdy jego połowę. Ramka rośnie więc samoczynnie na całość, której
  dotyka: na cały zastępnik, cały pas albo, na zeskanowanej kartce, na
  całą zaciemnioną powierzchnię. Mniejsza niż wyciągnięta ramka nigdy
  się nie staje.

- **Zaciemnianie odbywa się teraz słowo po słowie.** Ramka nad połową
  słowa zaciemniała dotychczas też tylko połowę – a w połowie
  zaciemnione nazwisko wciąż jest nazwiskiem. Dotknięte słowa są teraz
  usuwane w całości; sąsiad pozostaje nienaruszony.

- **W tekście i arkuszach wystarczy kliknięcie w zastępnik.** „Przywróć
  wybór” wymagało dotychczas dokładnego zaznaczenia zastępnika wraz z
  nawiasami kwadratowymi. Teraz wystarczy postawić kursor w środku;
  zaznaczenie widocznie przeskakuje na cały zastępnik.

- **Belgia doszła jako kraj.** Wybieralna w ustawieniach; rozpoznawane są
  wtedy belgijskie numery telefonu, numer rejestru krajowego (z cyfrą
  kontrolną), numer BTW/przedsiębiorstwa (z cyfrą kontrolną), adresy w
  obu językach urzędowych oraz kod pocztowy z miejscowością. Dotychczas
  belgijskie numery telefonu pozostawały, ponieważ kraj w ogóle nie
  figurował w katalogu.

- **Kanał aktualizacji mówi teraz, jak wcześnie dostają Państwo nowości –
  nie, jak daleko.** Kto stał na „Wersji testowej”, w ogóle nie dostawał
  oferty nowej wersji zapoznawczej ani nowej wersji stabilnej i musiał
  ręcznie zmienić kanał, żeby w ogóle się o tym dowiedzieć. Teraz
  oferowane jest też wszystko, co jest bardziej wiarygodne: wersja
  testowa przyjmuje wersje testowe, zapoznawcze i stabilne, wersja
  zapoznawcza przyjmuje zapoznawcze i stabilne. Odwrotnie nigdy – przy
  wersji zapoznawczej nie jest oferowana wersja testowa, nawet jeśli
  jest nowsza.

- **W oknie ustawień wiersze stoją dalej od siebie.** Cztery strony
  używały własnych odstępów zamiast siatki obowiązującej w reszcie
  programu; szczególnie na stronie „Rozpoznawanie” pola wyboru stały
  przez to wyraźnie za blisko siebie.

### Naprawione

- **Wypełnione formularze PDF nie pojawiają się już puste przy ręcznej
  obróbce.** Maskuro zamienia w tym celu wyłącznie ulotną kopię roboczą
  na statyczne strony: wpisane wartości stają się widoczne i dają się
  naprawdę zaciemnić; odczytywalne pola formularza nie pozostają ukryte
  w pliku. Oryginał pozostaje interaktywny i niezmieniony.
  Dotyczy to teraz też dynamicznych formularzy XFA: obsługujący XFA
  PDFium buduje najpierw wartości i podziały stron, następnie powstaje
  nowy PDF wyłącznie ze statycznych stron obrazowych. Jeśli budowa XFA
  się nie powiedzie, plik jest bezpiecznie odrzucany zamiast otwierany
  pozornie pusty.

- **„Anuluj” działa teraz też podczas dokładniejszego rozpoznawania.**
  Dotychczas przycisk blokował się po kliknięciu, ale przebieg liczył
  dalej aż do ostatniego bloku – przy długim pliku to minuty bez
  wyjścia, a przycisk wyglądał przy tym, jakby zadziałał. Teraz przebieg
  kończy się przy następnym bloku.

- **W plikach CSV nazwiska są teraz znajdowane także wtedy, gdy nie
  stoi przed nimi spacja.** W `P-1000;Brunnthaler, Elisabeth` numer
  personalny przykleja się przez średnik do nazwiska, a dla
  rozpoznawania było to jedno słowo bez nazwiska w środku – w listach
  personalnych przez to, w zależności od wiersza, całe nazwisko
  pozostawało. Numery telefonu, formuły i liczba kolumn pliku pozostają
  tym nienaruszone.

- **Nazwisko, którego zarówno imię, jak i nazwisko noszą łącznik, jest
  teraz rozpoznawane.** „Marie-Luise Habsburg-Ott” pozostawało w środku
  zdania, podczas gdy „Dragan Mitrović” w tym samym zdaniu było
  znajdywane – akurat kombinację dwóch połączonych połówek przeoczał
  model językowy. Połączone rzeczowniki jak „Połączenie Północ-Południe”
  czy „Programista-Deweloper” pozostają tym nienaruszone.

## 0.10.30-beta.1 – 18 sierpnia 2026

### Ulepszone

- **Rozmiar czcionki widoku tekstu można teraz widocznie ustawiać.** Suwak
  w prawym dolnym rogu, który dotychczas powiększał tylko podgląd strony,
  ustawia w oknie poprawek przy plikach tekstowych i biurowych rozmiar
  czcionki (50–300%) – tak samo „Powiększ”/„Pomniejsz” w menu Widok.
  Ctrl+kółko myszy działało już zawsze, ale wiedział o tym tylko ten, kto
  spróbował; teraz suwak, wyświetlacz i kółko działają razem.

- **W ciemnym wyglądzie leży teraz biała kartka na ciemnym blacie
  roboczym.** Dotychczas było odwrotnie: wokół kartki pozostawała jasna
  powierzchnia, a sam tekst stał jasno na ciemnym. Teraz kartka pozostaje
  w obu wyglądach papierowobiała z czarnym pismem – jak strona PDF, która
  w trybie ciemnym też nie robi się ciemna – a powierzchnia wokół jest
  ciemna.

### Naprawione

- **Po zaciemnieniu w środku zdania reszta zdania już się nie gubi.** Kto
  w oknie poprawek trzykrotnie sięgał w to samo miejsce – zastąp, zaciemnij,
  potem „Przywróć oryginał” – dostawał usunięty początek zdania: z
  „Pytania proszę kierować do działu księgowości.” robiło się „proszę
  kierować do działu księgowości.”, bez ostrzeżenia. Dotyczyło to każdego
  miejsca, w którym już raz coś usunięto z środka wiersza.

- **Błąd startu nie ciągnie już za sobą zakończenia.** Gdy budowa okna
  głównego się przerywała, zawieszało się potem też zakończenie przez
  ikonę paska zadań – a ten drugi błąd zasłaniał w raporcie błędów
  właściwą przyczynę. Teraz program kończy się czysto także z na wpół
  zbudowanego okna, a zapisane ustawienia pozostają przy tym nienaruszone.

- **„Przed/po” nie skacze już na początek dokumentu.** Kto w oknie
  poprawek przewinął w dół i przełączył na oryginał do porównania,
  lądował znów całkiem na górze – i musiał ręcznie odnaleźć miejsce.
  Widok pozostaje teraz na tym samym wierszu, w obu kierunkach.

- **Przy zaciemnianiu w wierszach wyjustowanych pozostawała ostatnia
  litera.** Gdy polecenie tekstowe rysuje więcej glifów, niż biblioteka
  odczytu zgłasza znaków – w justowaniu chętnie połyka spację –
  przyporządkowanie przesuwało się o jeden, a z „Dr. Michael Handler aus
  Willendorf” robiło się „[NAZW] r aus f”: dwie pozostałe litery w
  środku oczyszczonego zdania (znalezione w prawdziwym protokole rady).
  Przyporządkowanie jest teraz sprawdzane na podstawie brzmienia samego
  polecenia tam, gdzie jest ono czytelne – tam już się nie zgaduje.

- **„Lerchenfelder Gürtel 43/12” było usuwane tylko w połowie.** Wzorce
  adresowe nie znały ani Gürtel, ani Kai, ani Lände, ani Zeile, ani
  Markt, ani Graben jako rzeczownika podstawowego ulicy, a numer domu nie
  mógł nieść części z ukośnikiem (43/12, dom/drzwi) – numer pozostawał
  obok zastępnika. Oba uzupełnione; adresy wiedeńskie i salzburskie
  padają teraz w całości.

- **Zapisane strony internetowe pozostają uruchamialne po
  oczyszczeniu.** Adresy, które leniwe ładowanie odkłada w atrybutach
  data (`data-lazy-src`, `data-lazy-srcset`), były zastępowane jako
  odsyłacze – na prawdziwej stronie gminy szesnaście sztuk – i obrazy
  strony potem się nie ładowały. Adresy internetowe pozostają tam teraz,
  tak jak w `src` i `href` również; nazwiska, adresy e-mail i numery
  telefonu w atrybutach data są nadal zastępowane.

- **Dokumenty japońskie i koreańskie były przetwarzane jako chiński.**
  Rozpoznawanie języka wrzucało wszystkie trzy pisma do jednego worka,
  nie znajdowało w tekście japońskim (bez spacji) i koreańskim (z
  przyklejonymi partykułami) słów funkcyjnych – i brało po prostu
  pierwszy język CJK z katalogu. Japoński protokół rady i koreański
  protokół posiedzenia były przez to czytane modelem chińskim. Teraz
  decyduje sam obraz pisma: kana oznacza japoński, hangul oznacza
  koreański.

- **Dalsze pomyłki z testu terenowego w dziesięciu kolejnych językach:**
  urzędy jak „Primar”, „Gradonačelnik”, „Ordfører”, „Başkanı” czy
  „Δήμαρχος” nie liczą się już jako nazwiska osobowe; tureckie etykiety
  pól („Adı”, „Soyadı”) i greckie słowa rozmowy („Ωραία”, „Βεβαίως”) już
  nie padają; numery uchwał i paragrafów z datą („323/25-6-2008”, „27
  30.09.2024”) nie są już numerami telefonu; a fragmenty zdań z kropką
  („10.An”, „T.U.EE”, „…pa”) nie są już zastępowane jako adresy
  internetowe.

### Nowe

- **Raporty sprawdzeń automatycznie na życzenie.** Znacznik w
  ustawieniach (strona „Program”) odkłada po każdym oczyszczeniu sam z
  siebie plik PDF z raportem sprawdzenia – ze znacznikiem czasu w
  nazwie, we własnym folderze, nigdy obok wyniku. Kartki nie da się
  utworzyć wstecznie; kto potrzebuje jej do akt, ma ją dzięki temu
  zawsze. Domyślnie odkładanie jest wyłączone.

- **Dziennik sprawdzeń można teraz włączyć w programie.** Przy wczytaniu
  licencji firmowej Maskuro pyta raz, czy dziennik ma być prowadzony –
  dowód niesie wartość tylko wtedy, gdy działa od samego początku. Do
  tego jest przełącznik w ustawieniach (strona „Program”, widoczna z
  licencją firmową lub w okresie testowym); plik wytycznych zarządu
  obowiązuje dalej i może wymusić wartość jak dotychczas. Własny wiersz
  dziennika „włączono” zapisuje, od kiedy jest prowadzony – tym samym
  udokumentowany i podpisany jest też początek rejestrowania. Domyślnie
  dziennik pozostaje wyłączony.

- **Panel wskaźników pokazuje, co zrobił poziom SI.** Nowy wiersz podaje,
  ile niepewnych trafień model ocenił, zachował i odrzucił oraz ile
  dodatkowo znalazł – dotychczas jego praca była niewidoczna, jeśli nie
  klikało się w każdą wartość w edytorze poprawek. Tylko liczby, nigdy
  wartości ani uzasadnienia; bez pracy SI wiersz się nie pojawia.

- **Przywracanie działa teraz też w e-mailach i stronach HTML.** W
  plikach `.eml`, `.msg` i zapisanych stronach internetowych zastępnika
  nie dało się dotychczas cofnąć – aplikacja mówiła to uczciwie, ale
  właśnie e-mail jest formatem z najwięcej danymi osobowymi. Teraz
  przywracanie działa tam tak samo: z panelu trafień, z zaznaczonym
  wyborem i też przy zanonimizowanych zastępnikach. Niewidoczna gałąź
  HTML e-maila (to, co Outlook naprawdę pokazuje) jest przy tym
  ciągnięta razem, żeby widok i wiadomość mówiły to samo.

- **Panel trafień przywraca też zanonimizowane wartości – dla każdej
  osobno.** „Cofnij zastąpienie” było dotychczas przy zanonimizowanych
  plikach zablokowane, ponieważ „[NAZWISKO]” oznacza jednocześnie
  wszystkie nazwiska. Teraz przywracanie sprawdza w oryginale, które
  miejsce należy do której wartości – w PDF przy współrzędnych miejsca
  znalezienia, w widoku tekstu przez porównanie z oryginałem – i
  przywraca dokładnie miejsca wybranej wartości. Wiersze pozostałych
  wartości pozostają.

- **Także zanonimizowane zastępniki da się przywracać pojedynczo.** Przy
  anonimizacji wszystkie dane danego rodzaju nazywają się tak samo –
  „[NAZWISKO]” oznacza każdą osobę, i dotychczas znaczyło to: pojedyncze
  przywracanie nie działa. Teraz sprawdzane jest w oryginale, który i
  tak leży obok wyniku: w widoku tekstu zaznaczyć zastępnik i wybrać
  „Przywróć wybór” – wraca dokładnie to miejsce z dokładnie swoją
  wartością. Jeśli wartości z oryginału nie da się odczytać bez
  wątpliwości, aplikacja to mówi, zamiast zgadywać. Plik
  przyporządkowania nadal przy tym nie powstaje.

- **Okno poprawek otwiera się po oczyszczeniu samo z siebie.** Żadne
  narzędzie nie znajduje wszystkiego – dlatego sprawdzające spojrzenie
  na wynik należy do przypadku zwykłego, nie do dodatkowego kliknięcia.
  Kto tego nie chce, wyłącza to w ustawieniach pod „Rozpoznawanie”
  („Pokaż wynik potem w oknie poprawek”).

### Ulepszone

- **Wybór kraju stoi teraz na „samoczynny”.** Dotychczas fabrycznie
  obowiązywał obszar językowy interfejsu – na niemieckim komputerze więc
  także dokumenty niderlandzkie czy francuskie były oczyszczane tylko
  rozpoznawaniami DACH, a adres jak „Universiteitslaan 1” pozostawał
  (znaleziono w prawdziwych, publicznych protokołach rady). Teraz wybór
  kraju kieruje się językiem dokumentu; kto w ustawieniach dokonał
  stałego wyboru, zachowuje go.

- **Mniej błędnie zaciemnionych.** Szereg pomyłek, zmierzonych na
  korpusie testowym i na prawdziwych protokołach posiedzeń w sześciu
  językach, odpada: nazwy firm z formą prawną („Musterfirma GmbH”) nie
  liczą się już jako osoba lub miejscowość, tylko jako organizacja;
  formuły pożegnalne i nagie formy grzecznościowe („Saygılarımızla”,
  „Buenas tardes”, samodzielne „Pani”) nie są już nazwiskami; urzędy
  („Burmistrz”, „Sindaco”, „Alcalde”) pozostają; numery ustaw i uchwał
  („39/2015”) i kwoty z kropką tysięczną („330.000”) nie są już numerami
  telefonu; początki zdań jak „Envíame” czy „Estarei” nie padają już
  jako nazwisko; trafienie przez pusty wiersz nie liczy się już jako
  nazwisko. Numer faktury pozostaje jako dana dowodu księgowego – numer
  klienta i sygnatura akt padają nadal.

- **Przed wczytaniem modelu SI stoi teraz, do czego on służy.** Okno
  dialogowe doładowania nazywa zadania modelu – ocenianie granicznych
  trafień, znajdowanie dodatkowych nazwisk, proponowanie reguł i
  profili – i mówi otwarcie, że nie jest asystentem czatu. FAQ
  odpowiada na to samo pytanie obszernie („Co potrafi poziom SI – a
  czego nie?”), we wszystkich wersjach językowych.

### Naprawione

- **Raporty sprawdzeń PDF z wiersza poleceń da się teraz przeszukiwać.**
  Pod Windows bezgłowa droga PDF startowała bez ani jednej czcionki –
  każdy znak był rysowany jako pole zastępcze, a kartka nie niosła
  odczytywalnego tekstu: kto chciał w niej szukać lub coś skopiować, nic
  nie znajdował. Teraz raport w tym przypadku doładowuje czcionki
  systemu; tekst jest osadzony i odczytywalny. Raporty z okna nigdy tym
  nie były dotknięte.

- **„Przywróć oryginał” nad kilkoma wierszami skanu pozostawiało czarne
  paski między wierszami.** Na stronie zamienionej na obraz ramka
  sprzątała tylko same pasma wierszy; resztki wcześniejszego zaciemnienia
  pozostawały w lukach między nimi. Teraz wyciągnięta ramka dzieli się w
  pełni na wiersze.

- **Druga ramka nad zastępnikiem pozostawiała czerwoną resztkę.**
  Zastępnik jest niemal zawsze szerszy niż słowo, które reprezentuje;
  kto potem zaciemniał to samo miejsce, trafiał tylko jego początek –
  pozostawał fragment jak „RIFF_1]” w środku zdania, a przywracanie
  wstawiało potem tekst oryginału na jego miejsce zamiast na miejsce
  słowa. Naderwany zastępnik pada teraz zawsze w całości.

- **Na obróconej stronie zaciemnianie nad zastępnikiem usuwało
  niepowiązane zdanie.** Dorysowany później zastępnik był przy usuwaniu
  mylony z tekstem przed nim: on sam pozostawał, przychodziło ostrzeżenie
  „nadal stoi w dokumencie” – a w innym miejscu strony bezpowrotnie
  znikało zdanie, które z ramką nie miało nic wspólnego. Zastępnik jest
  teraz odnajdywany po swoim brzmieniu; łańcuch „zastąp, zaciemnij,
  przywróć” działa dzięki temu też na stronach wciągniętych w poprzek.

- **Podręcznik w dziesięciu językach nadal radził `python3-tk`.** W
  usuwaniu usterek stało tam, że pod Linuksem brakuje może tkinter –
  rada z czasów przed interfejsem Qt, która już nikomu nie pomaga. Teraz
  we wszystkich wersjach stoi ten sam akapit co w niemieckim: brakuje
  bibliotek systemowych, których Qt potrzebuje do wyświetlania.

- **Rozdział licencyjny podręcznika stał we wszystkich szesnastu
  tłumaczeniach na starym stanie.** W dziesięciu językach czytało się
  tam jeszcze, że Windows Server potrzebuje licencji firmowej z
  dostępem serwerowym i że nie ma tam okresu testowego ani wersji
  darmowej – odkąd miejsce liczy człowieka, a nie maszynę, oba te
  stwierdzenia są nieprawdziwe. Brakowało tam ponadto wszędzie
  informacji o tym, kiedy obsadzone miejsce się zwalnia, że licencja
  potwierdza się regularnie i co jest przy tym przekazywane, a
  odblokowanie bez internetu stało tylko jako skrócona wersja bez trzech
  kroków i bez wskazówki, że komputer potem pracuje rok bez połączenia.

- **Siedem akapitów o poprawianiu brakowało w dziesięciu językach.** Kto
  czytał pomoc po duńsku, fińsku, francusku, włosku, niderlandzku,
  norwesku, polsku, portugalsku, szwedzku lub hiszpańsku, nie znajdował
  ani podglądu strony dla plików biurowych, ani „Zaciemnij ręcznie”, ani
  całego rozdziału o tym, jak program uczy się z korekty – wraz z
  tabelą trzech szerokości. W „Co jest rozpoznawane” brakowało tym samym
  dziesięciu wersjom drogi przez etykietę w dokumencie.

- **Z wczytaną licencją program już się nie uruchamiał.** Zamiast okna
  pojawiało się „Nie udało się uruchomić programu” – i to przy każdej
  licencji, bez względu na jaką. Przyczyną był wiersz w wyświetlaniu
  licencji, który ostrzega tuż przed upływem okresu testowego; sięgał on
  do czegoś, co nie było tam dostępne. Bez licencji – w okresie testowym
  i w wersji darmowej – błąd nie występował, dlatego dopiero teraz go
  zauważono.

- **W formularzu nazwy pól pozostają.** „Data urodzenia” i „Adres”
  znikały razem ze swoją wartością: zastępnik stał mały i czerwony w
  miejscu *nazwy pola*, pole pod nim pozostawało puste. Nazwa pola nie
  należy do danych – pozostaje teraz, a zastępnik stoi tam, gdzie stała
  wartość.

- **Tytuły dokumentów w obcym języku nie są już brane za nazwiska.** Nad
  włoskim formularzem stało „FATTURA”, nad hiszpańskim „PERMISO
  PARENTAL” – oba były zastępowane. Lista słów dokumentowych znała tylko
  niemieckie odpowiedniki.

- **Z faktury nie znika już żadna pozycja.** „Dopłata materiałowa 1
  84,00” było brane za adres i zastępowane zastępnikiem miejscowości –
  dowodowi brakowało potem wiersza. Wiersz kończący się kwotą jest
  pozycją, nie adresem; prawdziwe adresy („Hauptstraße 1 120,00”)
  pozostają nienaruszone.

### Zmienione

- **„Obserwuj folder …” i wiersz poleceń są na razie niedostępne.** Obie
  drogi są zbudowane i działają, ale żadna z nich nie jest wypróbowana w
  praktyce: obserwacja folderu nigdy nie przeszła testu na Windows, a
  wiersz poleceń daje skryptowi dwa tuziny przełączników, które nigdy
  nie działały u żadnego użytkownika. To, co bez nadzoru zmienia
  dokumenty, nie ma tego robić niesprawdzone – dlatego są wycofane,
  dopóki test nie zostanie nadrobiony. Wpis menu brakuje, a `--wache`
  nie stoi już w `maskuro --help`.

- **Pozostaje otwarte, co tylko czyta, a co i tak jest potrzebne.**
  Przebieg wyszukiwania (`--suchlauf`) i sprawdzanie (`--nachpruefen`)
  działają dalej w wierszu poleceń – nie zmieniają żadnego pliku. Tak
  samo start przez Eksplorator, menu kontekstowe, schowek i okno; nic
  się w tym nie zmienia.

- **„Pobierz ze skanera” ma teraz własny rozdział w podręczniku.**
  Dotychczas stał na końcu „Obserwuj folder”. Na Macu rada tam brzmiała,
  żeby dać obserwować folder; teraz brzmi, żeby przeciągnąć wczytane
  strony do okna.

### Naprawione

- **„Przywróć oryginał” nad kilkoma wierszami niszczyło strukturę.**
  Ramka nad zastępnikiem, niezmienionym tytułem stanowiska i drugim
  zastąpieniem wstawiała cały obszar na nowo jako **jeden** wiersz – z
  trzech wierszy powstawał jeden, a to, co się już nie mieściło,
  stawało się pasem. Teraz każdy wiersz jest przywracany osobno.

- **A niezmieniony tekst pozostaje przy tym nienaruszony.** Kto
  przeciąga nad zastąpieniem *i* zwykłym tekstem, odzyskuje tylko
  zastąpienie; reszta nie jest dotykana. Także ostatnia resztka starego
  zastępnika znika przy tym – wcześniej jego zamykający nawias
  pozostawał w środku zdania.

- **Przy zastępowaniu nie pozostają już resztki starego tekstu.** W
  pogrubionym nagłówku stało potem „1. R[POJĘCIE_2]ige [POJĘCIE_1] …
  che” – zastępnik siedział tam, ale obok sylaby oryginału. Sprzątany
  jest teraz obszar, który Państwo obrysowują, nie tylko pola słów w
  nim.

- **Anonimowy zastępnik nie jest już przywracany.** Przy anonimizacji
  każde nazwisko nosi to samo `[NAZWISKO]`. Przywracanie brało
  pierwszy z brzegu wpis i wpisywało go w każde miejsce znalezienia – z
  „Georg Aigner” robiło się „Anna Musterfrau”, więc błędne nazwisko w
  dokumencie. Teraz stoi tam, że nie da się już powiedzieć, o jaką dane
  chodziło; dokument pozostaje nienaruszony.

### Nowe

- **„Przywróć oryginał” działa teraz też na zrasteryzowanej stronie.**
  Jeśli strona została zamieniona na obraz, przychodziła dotychczas
  odmowa: przywrócony tekst znalazłby się pod obrazem strony. Teraz
  miejsce w obrazie jest sprzątane, a tekst na nie wpisywany – jak
  zastępnik na skanie. Treść pochodzi przy tym z pliku oryginału, a ten
  nie jest zrasteryzowany.

- **„Przywróć wybór” stoi teraz jako własny przycisk.** Działało to już
  wcześniej, ale tylko wtedy, gdy przypadkiem zaznaczyło się zastępnik i
  naciskało „Zastąp wybór” – funkcji, którą znajduje się tylko
  przypadkiem, dla użytkownika nie ma.

### Zmienione

- **W czystym tekście, CSV i wiadomościach Outlook nie ma już „Zaciemnij
  wybór”.** Te formaty nie mogą nosić pasa; przycisk wstawiał tam
  zastępnik i też to mówił – ale przycisk robiący coś innego, niż się
  nazywa, tam nie pasuje.

- **Narzędzie mówi teraz, gdy w tym miejscu nic nie może zdziałać.**
  Zastępnika nie da się zastąpić po raz drugi, nad zaciemnieniem nie
  jest wstawiany zastępnik, a tam gdzie stoi już oryginał, nie ma nic do
  przywrócenia. Dotychczas te ruchy robiły coś, co wyglądało na efekt,
  ale nim nie było.

## 0.10.29-alpha.20260817 – 17 sierpnia 2026

### Naprawione

- **W oknie poprawek działa teraz każda ramka, którą się ciągnie.** Kto
  pracował dwa razy w tym samym miejscu – najpierw zastąpił, potem
  zaciemnił, potem przywrócił oryginał – jego drugi i trzeci ruch
  przepadały bez śladu: wciąż uchwytna ramka poprzedniego ruchu je
  przechwytywała. To samo przy zmianie narzędzia, przy czym nawet po
  cichu dalej działało stare narzędzie.
- **Zbyt wąsko wyciągnięta ramka mówi, że jest za wąska.** Dotychczas
  podgląd rozświetlał słowo na czerwono, a po puszczeniu przycisku bez
  słowa nic się nie działo.

- **Wiadomości Outlook dają się wreszcie poprawiać.** Plik `.msg`
  pokazywał w oknie poprawek „Tego formatu nie da się tu wyświetlić” –
  był jedynym obsługiwanym formatem bez żadnej drogi do ręcznej obróbki.
  Teraz nadawca, odbiorca, temat i treść wiadomości stoją nazwane w
  widoku i dają się zaznaczać i zastępować jak w każdym innym formacie
  tekstowym.

- **„Zastąp wybór” pozostaje w e-mailu przy zaznaczeniu.** Kto zaznaczył
  nazwisko w tekście głównym, tracił przy tym też nadawcę i odbiorcę z
  nagłówków, a komunikat wymieniał inny zastępnik niż ten, który stał w
  tekście. Teraz zaznaczona wartość jest zastępowana wszędzie – także u
  nadawcy, jeśli tam stoi – a nic poza tym nie jest naruszane.

- **Ramka nad kilkoma wierszami nie niszczy już tekstu.** Dotychczas
  powstawał jeden jedyny zastępnik w jednym miejscu: z naciętego słowa
  przy nim przyklejała się reszta, a z drugiego wiersza tekst znikał
  bezpowrotnie – żadnego zastępnika, żadnego pasa, tylko luka. Teraz
  każdy wiersz dostaje swój własny zastępnik z wartością, która tam
  naprawdę stała.

- **„Przywróć oryginał” działa teraz też po zaciemnieniu.** Okno
  zgłaszało sukces, a tekst nigdy nie wracał: czarny pas liczył się jako
  przeszkoda, więc dla przywróconego tekstu nie było już miejsca. Pas
  teraz ustępuje, a przywrócony tekst stoi czarno jak zwykły tekst – nie
  czerwono jak zastępnik.

- **„Przywróć oryginał” w nietkniętym miejscu nic już nie robi.** Kto
  ciągnął ramkę nad tekstem, przy którym nic w ogóle nie zmieniono,
  dostawał tekst usunięty i wstawiony z powrotem mniejszy i przesunięty
  – zgłaszano sukces. Teraz stoi tam, że nie ma nic do przywrócenia.

### Nowe

- **Także w Word, Excel, PowerPoint, OpenDocument i tekście można
  zaciemniać.** Dotychczas było tam tylko „Zastąp wybór”; pas był
  zastrzeżony dla widoku PDF, bez żadnego powodu do tego. Tam gdzie pasa
  nie da się przedstawić – w czystym tekście i w wiadomości Outlook –
  wartość jest zastępowana zastępnikiem jak dotychczas, i tak też stoi w
  komunikacie.

- **Zaznaczenie zastępnika przywraca go.** W widoku tekstu (Word, Excel,
  PowerPoint, OpenDocument, tekst) wystarczy teraz zaznaczyć zastępnik i
  nacisnąć „Zastąp wybór”: wraca pierwotna wartość. Dotychczas okno
  odsyłało w tym celu do panelu trafień.

- **Mówcy w protokole spotkania są rozpoznawani także wtedy, gdy ich
  nazwisko jest jednocześnie zwykłym słowem.** „Gruber: Odbiór nastąpi w
  przyszłym tygodniu.” było zastępowane, „Bauer: Zgadzam się.”
  pozostawało – nazwisko wygląda dla rozpoznawania jak rzeczownik.
  Wiersze pamiątkowe tej samej budowy pozostają nienaruszone: z „Uwaga:
  Instalację należy wyłączyć.” nie powstaje nazwisko.

- **„Używają Państwo najnowszej wersji” było mówione także wtedy, gdy w
  ogóle nie dało się sprawdzić.** Jeśli serwer aktualizacji odrzuca
  zapytanie – bo z tego samego adresu internetowego przyszło zbyt wiele
  zapytań albo bo sam akurat ma awarię – to program stał nieruchomo na
  swojej starej wersji i twierdził, że jest najnowsza. Dokładnie to
  wydarzyło się 17 sierpnia na komputerze Mac: 0.10.25 pozostawało,
  podczas gdy 0.10.28 od godzin było gotowe.

  Teraz okno mówi, co się dzieje, podaje godzinę następnego sprawdzenia
  – i wyraźnie wskazuje, że **nie** jest ustalone, czy własna wersja jest
  najnowsza.

  Zwykle nie leży to po stronie własnego komputera: przy wielu łączach
  liczni klienci dzielą ten sam adres internetowy, a serwer liczy ich
  razem. Dlatego Maskuro szuka w tym przypadku listy wersji **drugą
  drogą** i mimo to zwykle znajduje nowe wersje. Jeśli mimo to zostaje
  przy odmowie, serwer jest zostawiany w spokoju do podanej godziny –
  nawet jeśli przycisk zostanie naciśnięty jeszcze raz; ponawianie tylko
  przedłuża blokadę.

- **Dane ilościowe nie są już brane za nazwy miejscowości.** W umowie o
  pracę „Czterodniowy tydzień pracy” znikało za zastępnikiem
  miejscowości – w środku przedmiotu umowy. Takie połączenia wyrazowe z
  liczby i łącznika („Plan trzypunktowy”, „Dyżur 24-godzinny”) pozostają
  teraz nienaruszone. Adresy są z tego wyłączone: „Ulica Dwóch Braci”
  jest nadal zastępowana.

## 0.10.28-alpha.20260817 – 17 sierpnia 2026

### Zmienione

- **Miejsca licencji są teraz naprawdę liczone.** Dotychczas żadne
  stanowisko nigdy nie zgłaszało się w usłudze licencji – licencja na
  dziesięć miejsc działała na dowolnej liczbie komputerów, bez wiedzy
  kogokolwiek. Nowość: komputer, który uruchamia program, zajmuje jedno
  miejsce; miejsce zwalnia się samo po **siedmiu dniach bez
  uruchomienia**, więc zepsute urządzenie lub odchodzący pracownik nie
  blokuje niczego na stałe.

  Mały nadmiar jest przy tym **tylko pokazywany, a nie blokowany**: do
  dziesięciu procent powyżej zakupionej liczby wszyscy pracują dalej –
  nowy laptop obok wciąż zalogowanego starego nie ma być sprawą dla
  infolinii. Kto dołącza ponad to, wraca na wersję darmową i dostaje o
  tym informację; komputery, które były pierwsze, niczego nie
  zauważają.

- **Zakupiona licencja potwierdza się regularnie.** Jeśli nie uda się to
  przez **30 dni**, obowiązuje przez ten czas z powrotem wersja darmowa,
  dopóki się nie uda ponownie. Nic nie jest wyłączane, a od tygodnia
  wcześniej w oknie stoi wskazówka. Gdy tylko komputer wróci do
  internetu, załatwia się to samo. Okres testowy i wersja darmowa nadal
  w ogóle niczego nie zgłaszają – kto nigdy nie kupuje, nigdy nie
  dzwoni.

- **„Odblokuj bez internetu” wreszcie działa.** Odblokowanie było
  dotychczas wprawdzie sprawdzane i zapisywane, ale potem przez nikogo
  nie odczytywane – niczego nie zmieniało w uprawnieniach. Teraz jest
  wyjściem dla komputerów bez dostępu do sieci: obowiązuje przez **rok**,
  potem pobiera się z nowym kodem żądania nowe. Urządzenie z internetem
  potrzebne jest do tego raz w roku – sam komputer pozostaje trwale
  offline.

- **Odblokowanie działa teraz też z konta klienta** – pod „Moje licencje”
  na stronie. Stoi tam ponadto, które komputery są przypisane do
  Państwa licencji i kiedy ich miejsca się zwolnią; dotychczas nie było
  tego nigdzie widać. Strona bez logowania pozostaje dla wszystkich,
  którzy nie mają dostępu do sklepu – wymaga za to dodatkowo adresu
  e-mail z zamówienia, żeby sam klucz licencyjny nie wystarczał.

- **A w oknie stoi teraz, dokąd z kodem żądania.** Droga papierowa
  mówiła „wpisać na urządzeniu z połączeniem internetowym” i nie
  podawała adresu; strona odblokowania istnieje od dawna, ale nie była
  znikąd połączona linkiem. Teraz w oknie dialogowym, w podręczniku i w
  FAQ stoi **maskuro.com/lizenz-freischalten** – oraz na stronie pod
  kluczem licencyjnym.

- **Przycisk „Odblokuj bez internetu …” pozostaje widoczny**, nawet gdy
  licencja akurat nie obowiązuje. Wcześniej znikał razem z nią – więc
  dokładnie wtedy, gdy jest potrzebny.

- **„Wszystkie miejsca zajęte” mówi teraz prawdę.** Wskazówka kończyła
  się słowami „Program działa dalej bez zmian”; to już nieprawda, gdy
  nie przydzielono żadnego miejsca. Stoi tam teraz, że do odwołania
  obowiązuje wersja darmowa.

### Nowe

- **Przy włączaniu oczyszczania schowka stoi teraz obok, że trzeba
  sprawdzić.** Komunikat przytacza odtąd to samo zdanie, które stoi też
  przy wyniku pliku: Maskuro nie w każdym przypadku rozpoznaje wszystkie
  dane osobowe.

  Tutaj waży ono ciężej niż gdzie indziej. Przy pliku widzi się wynik,
  zanim się go przekaże dalej. Przy schowku nie – kopiuje się, wkleja, a
  oczyszczony tekst stoi już w oknie poczty. Komunikat mówi więc
  wyraźnie, żeby przejrzeć **wklejony** tekst.

  Pojawia się przy włączaniu, nie przy każdym kopiowaniu: to, co
  pojawiałoby się pięćdziesiąt razy dziennie, po trzecim razie nikt już
  nie czyta.

- **„Kopiuj wszystko” pod listą – a „Usuń wszystko” odsuwa się.** Nowy
  przycisk umieszcza wszystkie gotowe wyniki naraz w schowku, do
  załączenia do wiadomości lub wklejenia w innym programie. Dotychczas
  było to możliwe tylko przez menu i tam też tylko dla **zaznaczonych**
  wierszy – kto miał na myśli wszystkie, musiał najpierw nacisnąć
  Ctrl+A.

  Przy tym rząd przycisków jest na nowo uporządkowany: po lewej stoi
  to, co coś dodaje, po prawej za odstępem to, co coś usuwa. „Usuń
  wszystko” stało dotychczas bezpośrednio obok „Dodaj …”, a pomyłka
  kosztowała całą listę. Ta sama reguła obowiązuje od 13 sierpnia już
  przy każdym gotowym wierszu.

- **Stanowiska bez internetu dostają teraz swoje modele językowe z
  firmy.** Oczyszczanie działało tam zawsze bez połączenia – doładowanie
  modelu językowego nie, a model waży kilkaset megabajtów.

  Zarząd zestawia raz pliki na komputerze z połączeniem i kładzie je na
  udostępnionym zasobie, w wdrożeniu lub na pendrive. Miejsce jest
  wpisywane centralnie (pole `modellquelle` w `vorgaben.json` lub zmienna
  środowiskowa `MASKURO_MODELLQUELLE`). Od tego momentu każde
  doładowanie sięga najpierw tam – modele językowe, japoński słownik i
  poziom Wysoki – i idzie do sieci tylko wtedy, gdy pliku brakuje.

  Sumy kontrolne obowiązują przy tym bez zmian. Udostępnienie pliku w
  firmie jest często łatwiejsze do opisania niż wydanie w sieci; nie ma
  stać się wygodniejszą drogą do podstawionego modelu.

  Jak powstaje taki zasób i jak działają licencja i odblokowanie bez
  internetu, stoi w `OFFLINE.md`.

- **„Przywróć oryginał” – ramka przywraca to, co usunięto za dużo.** W
  oknie poprawek jest nowe narzędzie: przeciągnąć ramkę nad miejscem, a
  tekst wraca taki, jaki stał w oryginale.

  Zamyka to lukę, którą pozostawiał panel trafień. Tam zastąpienie dało
  się cofnąć tylko wtedy, gdy jego zastępnik był jednoznaczny – więc nie
  przy anonimizacji, gdzie „[NAZWISKO]” stoi przy każdej takiej danej, i
  w ogóle nie przy zaciemnionych miejscach, gdzie nie pozostaje żaden
  zastępnik. Właśnie tam gromadzą się pomyłki: „Użytkownik”, „Numer
  inwentarzowy”, „Podpis” chętnie brane są za nazwiska.

  Ramka nie potrzebuje zastępnika: **miejsce** pochodzi z prostokąta,
  **treść** z pliku oryginalnego – tego samego, który pokazuje
  przełącznik przed/po. Anonimizowane czy pseudonimizowane nie ma już
  przy tym znaczenia.

  Przywrócony tekst stoi czarno, nie czerwono: jest znów jawnym tekstem,
  nie zastępnikiem. Z listy trafień wpis znika dopiero wtedy, gdy jego
  zastępnik **nigdzie** już nie stoi w dokumencie – jeśli ta sama
  wartość została zastąpiona w kilku miejscach, pozostaje dla
  pozostałych.

  Na stronie, która została zamieniona na obraz, narzędzie odmawia i
  wyjaśnia dlaczego: przywrócony tekst znalazłby się pod obrazem strony
  i nie byłby widoczny.

### Naprawione

- **Przy zwijaniu „Szczegółów” i „Wskaźników” na ekranie pozostawały
  resztki obrazu.** Po zwinięciu część treści przesuwała się pod dolną
  krawędź okna i pozostawała tam nad tłem, dopóki nie narysowano nad tym
  czegoś innego.

  Oba obszary mają minimalną wysokość, żeby otwarte były użytecznie
  duże. Ruch przy zwijaniu obniżał jednak tylko wysokość maksymalną – a
  poniżej swojej wysokości minimalnej obszar się nie kurczy. Treść
  pozostawała więc wysoka na 200 punktów, podczas gdy okno kurczyło się
  już do 24; różnica stała pod krawędzią. Teraz wysokość minimalna
  ustępuje na czas ruchu i wraca potem.

- **Okno stawało się coraz mniejsze przy powtarzanym rozwijaniu i
  zwijaniu.** Przy rozwijaniu rośnie najwyżej do 92% wysokości ekranu;
  jeśli miejsca brakuje, rośnie więc mniej niż potrzeba. Przy zwijaniu
  mimo to odejmowało pełną kwotę z powrotem. Teraz oddaje dokładnie
  tyle, ile kosztowało rozwinięcie.

- **Resztka zaciemnionych danych mogła pozostać widoczna.** W życiorysie
  z „*30.12.1991” pozostawały czytelne w wyniku znaki „*30.1” – więc
  dzień i początek miesiąca daty urodzenia. Program nawet zauważył
  resztkę i dlatego zamienił stronę na obraz; właśnie to pogarszało
  sprawę, bo przez to resztka nie była już wprawdzie przeszukiwalna, ale
  nadal do odczytania – i nie do naprawienia.

  Przyczyna leżała między dwoma sprawdzeniami. Ostrzejsze z nich
  sprawdza, czy na powierzchni usuniętej danej stoi jeszcze coś, co tam
  nie należy; zgłasza swoje ustalenie jako zbiór znaków, ponieważ
  kolejność odczytu przesuwa się przy zastępowaniu. Rezerwowe
  rozwiązanie, które zamalowuje takie miejsca przed zamianą, szukało
  tego zbioru znaków jako tekstu na stronie – i nigdy go nie znalazło.
  Nic więc nie zostało zamalowane. Miejsce było znane przez cały czas i
  jest teraz przekazywane dalej, zamiast być szukane od nowa.

  Dotyczyło to każdej strony, której resztkę znajdowało wyłącznie to
  sprawdzenie – niezależnie od rodzaju pliku i języka.

- **Na skanie wciągniętym w poprzek rozpoznawanie tekstu nic nie
  znajdowało.** Kto wkłada kartkę bokiem do podajnika, dostaje plik, w
  którym pismo stoi obrócone o 90 stopni. Dotychczas Maskuro nie czytał
  w nim **ani jednej** danej – a plik potem wyglądał niepozornie:
  niczego nie znaleziono, więc niczego nie zgłoszono, a adres stał nadal
  czytelny na obrazie. Teraz rozpoznawanie tekstu samo prostuje stronę;
  na obrazie kontrolnym znów widać wszystkie dane.

  Dwie granice wyraźnie nazwane: kartka stojąca **do góry nogami** (180
  stopni) nadal nie jest czytana, a przy bardzo złym skanie prostowanie
  nie pomaga – tam za mało da się odczytać, żeby w ogóle ustalić
  położenie. Każdy obraz potrzebuje na to około jednej piątej dłużej.

### Zmienione

- **„Instaluj automatycznie” nazywa się teraz tak, jak działa.** Znacznik
  w ustawieniach obiecywał więcej, niż spełniał: pobiera nową wersję
  sam z siebie i uruchamia instalację – ta przebiega jednak
  **widocznie** i chce potwierdzenia, pod Windows wraz z zapytaniem
  Kontroli konta użytkownika. Kto czytał „automatycznie”, liczył na
  komputer, który sam się aktualizuje w nocy, a rano stawał przed
  kreatorem instalacji. Znacznik nazywa się teraz „Samoczynnie pobieraj
  aktualizacje i uruchamiaj instalację”, ze zdaniem pod spodem, co to
  oznacza. W zachowaniu nic się nie zmienia – to, że Maskuro nie
  wymienia się niepostrzeżenie, jest zamierzone i pozostaje tak.

## 0.10.27-alpha.20260817 – 17 sierpnia 2026

### Nowe

- **Nowość: `--ersetzen` do podłączenia oprogramowania kancelaryjnego.**
  Wynik zajmuje miejsce pliku źródłowego, zamiast powstawać obok. Dzięki
  temu wyewidencjonowanie i zaewidencjonowanie w oprogramowaniu
  kancelaryjnym („Otwórz i edytuj” w e-aktach) działa bez żadnego
  interfejsu: oprogramowanie wydaje plik i dostaje go z powrotem
  oczyszczony w tym samym miejscu.

  **Ten przełącznik obala pierwszą zasadę**, dlatego istnieje tylko w
  wierszu poleceń – nie w oknie – i tylko wtedy, gdy zwalnia go Państwa
  zarząd (wpis `ersetzen` w pliku wytycznych). Bez zwolnienia wywołanie
  przerywa się i mówi dlaczego; ciche utworzenie drugiego pliku byłoby
  gorszym błędem, bo wtedy niezmieniony plik zostałby ponownie
  zaewidencjonowany.

  Zapisywany jest najpierw plik sąsiedni; dopiero gdy jest gotowy,
  zajmuje miejsce źródła. Przerwanie lub błąd pozostawia więc źródło
  **bajt w bajt niezmienione** i nie pozostawia fragmentu. W dzienniku
  sprawdzeń zastąpienie stoi jako osobne pole – kontroler musi wiedzieć,
  że nieoczyszczona wersja już tu nie leży.

- **Podręcznik wyjaśnia teraz ostrzeżenie Windows przy pierwszym
  uruchomieniu.** Nowy pierwszy rozdział „Windows ostrzega przy
  pierwszym uruchomieniu – co robić”, z dwoma obrazami i trzema krokami:
  „Więcej informacji” to mały link, nie przycisk – dokładnie na tym
  utyka większość – potem „Uruchom mimo to”.

  To, że stoi tam „Nieznany wydawca”, jest całą treścią ostrzeżenia:
  pakiety są obecnie dostarczane bez certyfikatu. Uważamy, że lepiej to
  wyjaśnić, niż przemilczeć.

- **Droga powrotna zauważa teraz, gdy tekst i przyporządkowanie do siebie
  nie pasują.** Kto wkleja odpowiedź do innego procesu, dostawał
  dotychczas obce nazwiska w prawidłowym tekście – żadnego błędu, żadnego
  komunikatu, tylko błędnie. Maskuro zapamiętuje teraz, jakie zastępniki
  w ogóle stworzył ostatni przebieg, i zgłasza każdy, który do niego nie
  należy. Jeśli żaden nie pochodzi z ostatniego przebiegu, nic nie jest
  wstawiane, a okno mówi dlaczego – zamiast jak dotychczas przypuszczać
  upłynięty termin.

  **Granica pozostaje, i stoi też w podręczniku:** zastępniki są
  numerowane dla każdego przebiegu, pierwsze nazwisko nazywa się więc w
  każdym dokumencie `[NAZWISKO_1]`. Jeśli obcy tekst niesie tylko takie
  zastępniki, pomyłki nie da się rozpoznać.

- **PDF można teraz wydać czarno-biały.** Znacznik przy trybie działania
  zamienia każdą stronę w obraz czarno-biały – z niewidoczną warstwą
  tekstu pod spodem, więc nadal czytelny i przeszukiwalny. Do wysyłki
  przez beA i podobne drogi z twardymi limitami rozmiaru: na naszym
  korpusie pomiarowym średnio **o 68% mniejszy** (wiersz poleceń:
  `--monochrom`).

  **Ile to daje, zależy od dokumentu** – i to stoi też przy znaczniku:
  zeskanowane i bogate w obrazy kurczy się mocno, smukły dokument
  tekstowy bez osadzonych czcionek może nawet zrobić się większy.
  Proszę wypróbować na jednym pliku, zanim Państwo włączą to dla
  pakietu.

  Cena: każda strona jest liczona na nowo – przy tysiącu stron trwa to
  minuty. A ilustracje tracą wszystko między czernią a bielą; dla
  tekstu jest to obojętne, dla fotografii nie.

- **Lista trafień w oknie poprawek teraz liczy.** Nad listą stoi „5
  trafień”, a gdy tylko Państwo filtrują, „1 z 5 trafień”. To różnica
  między „przefiltrowałem” a „jest ich pięć, i widziałem wszystkie” –
  ruch, którym sprawdza się, czy nazwisko naprawdę wszędzie zostało
  zastąpione.

- **Dziennik sprawdzeń można teraz przeszukiwać i filtrować.** Widok
  pod „Plik → Dziennik sprawdzeń” miał dotychczas tabelę i nic poza tym
  – przy miesiącu z trzema tysiącami przebiegów widać było, że dużo się
  wydarzyło, ale nie co.

  Nowe są **pole wyszukiwania**, **trzy filtry** (procedura, wynik,
  rodzaj) i **przewijanie stron**, do tego trzy kolumny, których wcześniej
  nie było: **procedura** (zaciemnione lub zastąpione), **pewność** i
  **czas trwania**. Nad listą stoi, ile jest właśnie widocznych i ile
  filtr ukrywa.

  „Zapisz jako CSV …” podaje teraz **to, co jest widoczne** – kto
  przefiltrował, dostaje przefiltrowane, a komunikat podaje liczbę.

  Kreska przy pewności lub czasie trwania oznacza, że dla tego wiersza
  nic nie zmierzono – np. bo jest starszy niż ta funkcja. Te wartości
  **nie** są dodatkowo obliczane wstecznie. Filtra po użytkowniku nadal
  nie ma; pojedynczy wiersz mimo to znajduje wyszukiwanie.

### Usunięte

- **Wskazówka o przejrzystości w oknie „O tym programie” znów zniknęła.**
  Stała tam od 0.10.22-beta.1 i mówiła, że aplikacja została stworzona
  ze wsparciem sztucznej inteligencji. Nie jest nigdzie wymagana, a
  akurat w aplikacji do ochrony danych niektórzy czytali ją jako
  stwierdzenie o sposobie działania – więc tak, jakby dokumenty szły do
  usługi w sieci. Oczyszczanie odbywa się nadal wyłącznie na własnym
  komputerze; to stoi tam, gdzie należy, w zakładce „Ochrona danych”.

### Naprawione

- **Program zamieniał własny symbol na gorszy.** Kto wpisywał menu
  kontekstowe z poziomu programu, miał potem na pasku zadań inną tarczę
  niż po instalacji – podobną, ale z pasami wyrównanymi do lewej zamiast
  wyśrodkowanymi i widocznie grubszą. Kryło się za tym rozwiązanie
  awaryjne: jeśli program nie znajduje wzorca symbolu, rysuje sobie
  własny. Pomyślane było to na wypadek, gdy symboli **w ogóle** nie ma;
  faktycznie rysowało też wtedy, gdy dołączone leżały już od dawna – i
  je nadpisywało. W wersji zainstalowanej przez instalator wzorca nie
  ma, więc trafiało tam każdego. Istniejące symbole pozostają teraz
  nienaruszone.

  **Już dotknięte instalacje nie odzyskują właściwego symbolu same z
  siebie** – trzeba raz zainstalować ponownie.

- **„Identyfikacja obiektu: OB-4711-22” liczyła się jako nazwa
  logowania.** Rozpoznawacz nazw użytkownika sprawdzał swoje etykiety
  bez granicy słowa przed nimi – więc chwytał **każde** słowo kończące
  się na jedną z nich: identyfikacja obiektu, identyfikacja pojazdu,
  identyfikacja urządzenia. Wartość za nim była usuwana, mimo że z nazwą
  logowania nie ma nic wspólnego.

  Złożenia naprawdę pomyślane – „identyfikacja użytkownika”,
  „identyfikacja logowania” – stoją osobno na liście i są nadal
  znajdywane.

- **Po angielsku, grecku, japońsku i koreańsku szesnaście zastępników
  stało w wyniku po niemiecku.** Kto ustawił interfejs na jeden z tych
  czterech języków, dostawał dla nowszych rodzajów danych niemieckie
  etykiety wpisane do dokumentu – z hasła powstawało `[ZUGANGSDATEN_1]`
  zamiast `[CREDENTIALS_1]`, z klucza diagnostycznego
  `[DIAGNOSESCHLUESSEL_1]` zamiast `[DIAGNOSIS_CODE_1]`. Dotyczyło to
  zdrowia, diagnozy, medykacji, kluczy diagnozy i leku, religii, związku
  zawodowego, poglądów politycznych, prawa karnego, danych dostępowych,
  nazwy użytkownika, danych karty, współrzędnych, zawodu, kwoty i cechy.

  Pozostałe 44 języki nigdy nie miały tego błędu: pobierają swoje
  etykiety z plików językowych, w których te rodzaje stały od początku.
  Dokładnie te cztery języki prowadzą z innego powodu własne tabele –
  ich pismo nie przetrwa zestawu znaków PDF, dlatego stoją tam
  łacińskie etykiety – i w tych tabelach nowych rodzajów po prostu
  brakowało.

  Zauważono to przy tłumaczeniu strony katalogu: witryna obiecywała
  angielskim czytelnikom etykiety, których program nie pisał. Test
  kontrolny trzyma teraz cztery tabele wobec listy wszystkich etykiet,
  które w ogóle mogą powstać.

- **Okno reguł nie otwiera się już za małe na swoją treść.** W zakładce
  „Własne wzorce wyszukiwania” wiersz wyjaśniający asystenta („Szukane
  jest: …”) leżał w połowie za polem „Tekst próbny” – akurat zdanie, przy
  którym bez znajomości wyrażeń regularnych sprawdza się, czy własna
  reguła szuka właściwej rzeczy. Okno miało stały minimalny rozmiar z
  czasów mniejszej liczby zakładek i dało się przez to ściągnąć poniżej
  tego, co się mieści. Teraz kieruje się swoją treścią i otwiera się
  tylko tak małe, jak wszystko pozostaje czytelne.

- **Nazwiska w formułach arkuszy nie pozostają już.** Komórka ma więcej
  niż jedno miejsce dla tekstu, a dotychczas sprzątane było tylko jedno.
  Jeśli w formule stało nazwisko – `="Pani "&"Sieglinde Ortner"` – lub
  było ono ostatnio obliczonym wynikiem formuły, pozostawało niezmienione
  w skoroszycie, mimo że ta sama osoba w sąsiedniej komórce była
  zastąpiona. Kto klikał komórkę, czytał je w pasku edycji.

  Oba są teraz zastępowane. Dotykane jest tylko to, co stoi w cudzysłowie:
  odniesienia do komórek, nazwy funkcji i nazwy arkuszy pozostają
  nienaruszone, `=SUMA(K2:K6)` liczy dalej. Ponieważ to samo nazwisko
  wszędzie dostaje ten sam zastępnik, `=SUMA.JEŻELI(A:A;"Huber";B:B)`
  nadal znajduje swoje wiersze.

- **Wykresy nie pokazują już nazwisk.** Wykres zapisuje własną kopię
  swoich opisów osi – rysuje ją nadal, nawet gdy komórki źródłowe są już
  od dawna puste. Pod słupkami stało więc dalej pięć nazwisk osobowych,
  podczas gdy tabela powyżej była czysta. Dotyczy arkuszy **i**
  prezentacji.

- **Nazwane zakresy ze stałym tekstem są sprzątane.** Nazwany zakres
  może zamiast odniesienia do komórki zawierać stały tekst; jeśli stało
  tam nazwisko, pozostawało. **Nazwa** zakresu pozostaje nadal – odwołują
  się do niej formuły, a przemianowanie dałoby błąd odniesienia. Jak przy
  nazwie arkusza, jest zgłaszana, nie zastępowana.

- **Raz rozpoznana data urodzenia znika w całym dokumencie.** Sama data
  niczego nie mówi – dopiero słowo pola czyni ją datą urodzenia, i
  dokładnie dlatego data faktury zostaje w spokoju. Jeśli jednak ta sama
  dana stała w tym samym dokumencie po raz drugi bez tego słowa – w
  tytule obrazu, w wypełnionym polu formularza – pozostawała tam, mimo
  że kilka wierszy wyżej „urodzony dnia …” było rozpoznane bez wątpliwości.
  Przenoszone jest tylko to, co w **tym** dokumencie już zostało
  rozpoznane jako data urodzenia; zgadywane nadal nic nie jest.

- **Ustrukturyzowane dane w stronach internetowych zdradzają swoją datę
  urodzenia.** W bloku JSON-LD dla wyszukiwarek data stoi pod kluczem
  `birthDate` – klucz mówi, czym to jest, tak jak zwykle nagłówek
  kolumny. Jest teraz odczytywany; „Birthday” i „Birthdate” liczą się
  przez to też w formularzach jako oznaczenie pola.

- **Data urodzenia i numer personalny są znajdywane też w tabelach.** W
  komórce stoi tylko naga wartość – `14.03.1988`. Co ona oznacza, mówi
  wyłącznie nagłówek kolumny, a ten stoi wiele wierszy wyżej. W Excelu
  był on już odczytywany; w tabelach LibreOffice i w plikach CSV nie, i
  tam data urodzenia przez to pozostawała.

  Oba czytają teraz nagłówek – **ale tylko, jeśli on sam jest oznaczeniem
  pola**. Pod „Data urodzenia” data pada, pod „Data faktury” czy „Data
  dostawy” nie. To celowo ostrożna interpretacja: nagłówek jak „Nazwisko”
  nad dowolną uwagą już raz nałożyłby zastępnik na zdanie, w którym w
  ogóle nie występuje osoba.

### Naprawione

- **Oczyszczony CSV pozostaje tabelą.** Rozpoznawanie czyta wiersz CSV
  jako zdanie i przez to kładło już raz swoje znaleziska przez średnik.
  Zastępnik połykał separator, wiersz miał potem o jedną kolumnę mniej, a
  pliku nie dało się już otworzyć jako tabeli. Miejsca znalezienia
  kończą się teraz na granicy komórki, a cudzysłowy maskowania
  pozostają. Dotknięte komórki są potem jeszcze raz czytane osobno –
  inaczej sąsiednia komórka pozostałaby nieoczyszczona, którą zbyt
  długie trafienie zasłoniło.

- **Komentarze w prezentacjach.** Uwaga na marginesie slajdu – często
  dokładnie miejsce, gdzie stoi „Proszę zadzwonić do Pani … przed
  posiedzeniem” – pozostawała nietknięta, wraz z nazwiskiem tego, kto
  ją napisał. W Excelu oba były już sprzątane; PowerPoint odkłada tekst
  komentarza i autora inaczej, i to zostało przeoczone. Dotyczy obu
  budowli: starszej i tej, którą PowerPoint pisze od 2019 – tam też
  służbowy adres e-mail wiszący przy autorze. Inicjały, które PowerPoint
  pokazuje przy dymku, są usuwane razem.

- **Pliki LibreOffice: formuła, pole użytkownika, autor notatki.** To, co
  w Excelu było już sprzątane, pozostawało w tabeli ODS – tam formuła
  nie stoi jako osobny element, tylko jako właściwość komórki, i
  nazwisko w niej przeżywało. Przy następnym otwarciu LibreOffice
  liczyło je z powrotem.

  Do tego trzy dalsze miejsca: wartość **pola użytkownika** stoi w
  OpenDocument raz na górze w deklaracji i w tekście jest tylko
  wywoływana – zastępowane było dotychczas tylko wywołanie, więc przy
  otwarciu wracała stara wartość. **Autor notatki** i śledzonej zmiany
  pozostawał. A w **tabeli** śledzenie zmian w ogóle nie było sprzątane –
  inaczej niż w dokumencie tekstowym – więc usunięte treści komórek wraz
  z nazwiskiem edytora pozostawały zachowane. Odniesienia do komórek i
  formuły sumujące pozostają przy tym nienaruszone.

- **Zapisane strony internetowe zdradzają swoje atrybuty.** Strona nie
  pokazuje wcale wszystkiego, co zawiera. Wypełnione pole formularza
  niesie wpis w `value`, interfejs JavaScript odkłada swój zbiór danych
  w `data-…`, a blok dla wyszukiwarek (JSON-LD) powtarza go w pełni i
  poprawnie sformowany: nazwisko, data urodzenia, adres, telefon.
  Widoczny tekst był oczyszczony, wszystko to stało dalej.

  Teraz te miejsca też są sprzątane, do tego `aria-…` (co jest
  odczytywane czytnikowi ekranu), `placeholder`, `summary` i proponowana
  nazwa pliku odsyłacza. Blok JSON-LD jest przy tym czytany jako dane i
  pozostaje ważny – jego klucze i słownictwo pozostają, tylko wartości
  odchodzą. Zwykły JavaScript pozostaje nadal nietknięty.

- **Obrazy tracą swoje dane dodatkowe też bez EXIF.** Zdjęcie niesie
  obok siebie zapisane nazwisko fotografa, czas nagrania i współrzędne
  GPS miejsca nagrania – przy ogłoszeniu mieszkania zdradza to adres,
  nawet gdy w tekście żadnego nie ma. Było to usuwane, dopóki obraz miał
  EXIF. Jeśli jednak dane były odłożone **tylko** jako XMP (tak zapisują
  Lightroom i Photoshop) lub jako blok tekstowy w PNG (`Author`,
  `Comment`), obraz pozostawał całkiem nienaruszony. Oba są teraz
  rozpoznawane i usuwane – także przy obrazach tkwiących w dokumencie i
  w nim pozostających. Orientacja przeżywa nadal, a obraz bez danych
  dodatkowych nie jest niepotrzebnie zapisywany na nowo.

- **Cele odsyłaczy w arkuszach, prezentacjach i dokumentach Word.**
  Dokąd prowadzi odsyłacz, nie stoi w tekście, tylko we własnym
  składowisku pliku. Adres e-mail za „Napisz e-mail” przetrwał dlatego
  oczyszczanie nienaruszony, podczas gdy ten sam adres w tekście był
  zastąpiony. `mailto:` i `tel:` są tam teraz sprzątane tak samo jak w
  zapisanych stronach internetowych.

### Nowe

- **Listy lekarskie nie wracają już uszkodzone.** Dotychczas
  rozpoznawanie nazwisk brało substancje lecznicze za nazwiska osobowe:
  z „Metoprololsuccinat” powstawało `[NAZWISKO]`, z „Ramipril”
  powstawało `[MIEJSCE]`. Plan leczenia stawał się przez to nieużyteczny
  – podczas gdy diagnozy pozostawały nietknięte, więc dokładnie na
  odwrót. Zmierzono, że dotyczyło to **63% substancji czynnych** i **53%
  klinicznych terminów fachowych**, i nie tylko po niemiecku: w siedmiu
  językach 74%, po włosku wszystkie sprawdzone.

  Maskuro zna teraz słownictwo medyczne i zostawia je w spokoju.
  Pozostaje 6% zamiast 43% (niemiecki) i 1% zamiast 74% (dla wszystkich
  języków). Tam gdzie stoi przed tym forma grzecznościowa – „Szanowna
  Pani …” – nazwisko pozostaje nazwiskiem, nawet jeśli przypadkiem brzmi
  jak substancja lecznicza.

- **Choroby i leki można usuwać – jeśli Państwo chcą.** Nowy znacznik w
  ustawieniach: „Usuwaj też choroby i leki” (wiersz poleceń:
  `--mit-diagnosen`). Dla akt personalnych, wypowiedzeń i opinii, gdzie
  diagnoza nikogo nie dotyczy.

  **Domyślnie wyłączone**, i to celowo: list lekarski *składa się* z
  diagnoz i substancji czynnych. Kto go anonimizuje – do badań, do
  szkolenia, do narzędzia SI – chce zwykle dokładnie tę treść zachować i
  pozbyć się tylko tego, kogo dotyczy. Diagnoza jest tam ładunkiem, nie
  legitymacją.

  Rozpoznawanie znajduje popularne oznaczenia i nie zastępuje przeglądu:
  lista chorób nigdy nie jest kompletna, bo lekarz pisze „C2-Abusus”,
  tam gdzie klasyfikacja prowadzi „zaburzenia spowodowane alkoholem”.

- **Klucze diagnozy i leku są znajdywane.** ICD-10 (`I48.2`), ATC
  (`A10BA02`) i numer centrali farmaceutycznej to dane zdrowotne jak
  każda wypisana diagnoza – w listach wypisowych i dokumentach
  rozliczeniowych nawet częstsza forma. Są domyślnie włączone, jak
  pozostałe kategorie szczególne wg art. 9 RODO.

  Klucz diagnozy jest rozpoznawany tylko z dowodem: z „ICD” przed nim
  lub w nawiasie za wierszem diagnozy. Bez tego warunku program uznałby
  klawisz funkcyjny **F10** za diagnozę uzależnienia – w klasyfikacji
  F10 to dokładnie to.

- **Gotowy plik można teraz kopiować.** Przy każdym gotowym wierszu obok
  „Zobacz”, „Popraw” i „Pokaż w folderze” stoi czwarty przycisk:
  **Kopiuj**. Odkłada oczyszczony plik do schowka – stamtąd idzie
  Ctrl+V (Mac: ⌘V) do maila, okna czatu lub narzędzia SI, bez objazdu
  przez folder.

  Kopiowany jest **plik**, nie jego tekst: układ strony, obrazy i pasy
  zaciemniające pozostają zachowane. Przez menu kontekstowe listy do
  schowka idzie też kilka zaznaczonych wyników naraz, a w menu „Plik”
  stoi ta sama droga jako **„Kopiuj wynik”** dla wszystkich, którzy wolą
  klawiaturę.

- **Wybór kraju może teraz podążać za dokumentem.** Numery dowodu,
  ubezpieczenia i podatkowe różnią się od kraju do kraju, a które kraje
  są sprawdzane, było dotychczas ustalone na całą sesję – wyprowadzone z
  języka interfejsu. Kto pracuje po niemiecku i oczyszcza francuskie
  pismo, szukał w nim więc niemieckich ID podatkowych, a nie
  francuskiego numeru ubezpieczenia społecznego.

  W oknie reguł stoi do tego teraz **„Samoczynnie według języka
  dokumentu”**. Stały wybór pozostaje obok, i to celowo: rozpoznawanie
  języka nie jest nieomylne – gdy rozpozna błędnie, chwyta niewłaściwy
  wybór kraju. Kto przetwarza tylko akta jednego kraju, jedzie
  bezpieczniej ze stałą listą.

  Nienaruszone pozostają przy tym **niemieckie** wzorce (ID podatkowe,
  tablice rejestracyjne, numer wewnętrzny): zależą od języka, nie od
  wyboru kraju, i działają nadal też wtedy, gdy krótki niemiecki tekst
  jest zaklasyfikowany jako angielski.

- **Hasła, klucze i nazwy logowania są teraz znajdywane.** Kto kopiuje
  komunikat błędu, dziennik lub fragment pliku konfiguracyjnego do okna
  SI, ma tam prawie zawsze klucz dostępowy – a ten stał dotychczas
  niezmieniony.

  Rozpoznawane są oba: rozpowszechnione formy klucza mówiące same za
  siebie (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token,
  nagłówek klucza prywatnego), oraz forma opisana – „Hasło:”, „API-Key
  =”, „Token:”, „Nazwa użytkownika:”. Zastępowana jest przy tym tylko
  wartość, nigdy etykieta: „Hasło: [ZUGANGSDATEN_1]” pozostaje czytelne,
  a kto sprawdza wynik, widzi, że tam stało hasło.

  Nazwa logowania i hasło to dwa osobne rodzaje. Kto chce usunąć tylko
  hasła, wyłącza jeden i zachowuje drugi.

- **Kody kreskowe i QR w obrazach są zaciemniane.** Na zeskanowanym
  piśmie prawie zawsze przyklejony jest kod, a w nim stoi sygnatura akt
  – ten sam numer, który jest usuwany w tekście obok. Dotychczas
  maszynowo czytelna wersja pozostawała: pas nad numerem nic nie daje,
  jeśli dwa centymetry dalej urządzenie odczytuje go w sekundę.

  Rozpoznawane są QR-kod, Data Matrix, Aztec, Code 128, EAN i pozostałe
  popularne formy. Zaciemnianie oznacza pikselizację, i to grubszą niż
  przy twarzach: korekcja błędów kodu odzyskuje z niewielu zachowanych
  pól zaskakująco dużo, połowiczna zasłona nie byłaby usunięciem.

  Opcja stoi obok „Zaciemniaj twarze” i jest tak samo **domyślnie
  włączona**. Także przy wyłączonej opcji raport podaje, ile obrazów
  niesie kod – twarz widzi się przy przeglądaniu, kod uważa się za
  dodatek.

- **Numer weryfikacyjny karty, PIN i data ważności są znajdywane.**
  Numer karty kredytowej program znajdował już; dopiero z tymi trzema
  danymi obok jest użyteczny, a na każdym dowodzie rozliczeniowym stoją
  razem. Wszystkie trzy tylko za swoją etykietą – „123” samo w sobie to
  numer domu, numer strony lub liczba sztuk.

- **Współrzędne w tekście są znajdywane.** Z obrazów Maskuro usuwał
  miejsce nagrania już dotychczas; jeśli ta sama dana stała jako tekst
  w opinii lub raporcie interwencji, pozostawała. Rozpoznawane są
  stopnie dziesiętne i zapis stopnie-minuty-sekundy. Przy stopniach
  dziesiętnych w pobliżu musi stać słowo jak „Lokalizacja”, „Miejsce
  znalezienia” lub „Współrzędne” – inaczej każdy szereg pomiarowy z
  dwoma miejscami po przecinku byłby daną miejscowości.

- **Kwoty pieniężne można teraz usuwać razem.** Nowy znacznik „Usuwaj
  też kwoty pieniężne”, domyślnie **wyłączony** jak daty powyżej: w
  umowie kwota jest treścią, a kto zaciemnia wszystko, nikogo nie
  chroni. W rozliczeniu wynagrodzenia, propozycji ugody lub wyciągu z
  konta jest natomiast dokładnie tą daną, która mówi więcej o osobie niż
  nazwisko obok – wie to tylko ten, kto ma pismo przed sobą.

  Rozpoznawana jest kwota **tylko z oznaczeniem waluty**: „4.250,00”
  samo w sobie to liczba sztuk, dopiero „4.250,00 EUR” to pieniądze.
  Liczy się symbol waluty, skrót i pełna nazwa, przed i za, wraz z
  zapisem „990,– CHF”.

- **Kategorie szczególne wg art. 9 RODO są rozpoznawane.** Wyznanie
  religijne, przynależność związkowa, przekonania polityczne, dane
  zdrowotne – i obok dane karne wg art. 10. To dane, których
  przetwarzanie rozporządzenie zasadniczo **zakazuje**; są dlatego jako
  jedyna nowa grupa domyślnie **włączone**. Kto chce je zachować,
  decyduje o tym sam.

  Rozpoznawana jest forma, w jakiej stoją w praktyce: pole formularza
  na arkuszu personalnym – „Wyznanie: rzym.-kat.”, „Związek zawodowy:
  OPZZ”, „Stopień niepełnosprawności: 50”, „Karalność: brak” – zarówno
  z dwukropkiem obok, jak i z etykietą nad nimi, jak dostarcza je
  wypełniona kartka.

  **Tekst główny należy do poziomu SI.** „Od lat angażuje się w związku
  zawodowym” to ta sama dana, i żaden wzorzec wyszukiwania nie znajduje
  jej niezawodnie. Poziom SI od tego wydania szuka wyraźnie też tych
  kategorii; kto potrzebuje tekstu głównego, dołącza go.

- **Cechy osobowe i zawód – dane pokazujące, kto jest mowa, nawet bez
  nazwiska.** Płeć, stan cywilny, wzrost, kolor oczu i włosów są od tego
  wydania usuwane; zawód, funkcja i dział na życzenie, przez własny
  znacznik („Usuwaj też zawód i dział”) lub `--mit-berufen`.

  **Dlaczego jedno jest włączone, a drugie wyłączone:** „Kierowniczka
  działu zakupów” nazywa w firmie dokładnie jedną osobę, nawet gdy
  nazwisko obok jest zaciemnione – w opinii lub wypowiedzeniu należy to
  usunąć. Przegląd pracowników *składa się* natomiast z oznaczeń
  zawodowych; kto usuwałby je domyślnie, oddawałby pustą kartkę. Który
  przypadek zachodzi, wie tylko ten, kto ma pismo przed sobą. Cechy
  powyżej stoją niemal wyłącznie w polach formularza, są rzadkie i nigdy
  nie niosą treści – nic więc nie kosztują.

- **Sprawdzić obcy plik.** „Plik → Sprawdź plik …” czyta ponownie już
  zaciemniony dokument i zgłasza, co jeszcze w nim stoi – i **w którym
  miejscu**: strona i wiersz, rodzaj i długość. Na wypadek, gdy ktoś
  sprawdza pracę kogoś innego: akta z kancelarii, informację z urzędu,
  własną pocztę wychodzącą przed wysyłką.

  **Sama wartość nie stoi w raporcie.** Kto otwiera to miejsce, widzi ją
  i tak – a raport dzięki temu wolno zapisać i przekazać dalej, bez
  bycia samemu zbiorem danych osobowych.

  **A raport w każdym przypadku mówi, czego nie mógł zobaczyć.** Obrazy
  nie są czytane; przy skanie bez warstwy tekstu „brak miejsca
  znalezienia” oznacza *nie sprawdzone*, nie *czyste*. W wierszu poleceń
  rozdziela to wartość zwrotna: `--nachpruefen` zwraca 0 dla sprawdzone
  i czyste, 4 dla miejsc znalezienia i 5 dla niesprawdzalne. Dzięki temu
  pocztę wychodzącą można automatycznie wstrzymać, zamiast ją przepuszczać.

- **Raport sprawdzenia: kartka na każde oczyszczenie.** „Plik → Zapisz
  raport sprawdzenia …” – lub `--pruefbericht <folder>` w wierszu
  poleceń – zapisuje jednostronicowy PDF (opcjonalnie CSV lub tekst) z
  danymi o przebiegu, znalezionymi rodzajami wraz z liczbą, dwoma
  wskaźnikami i adnotacją sprawdzenia. Do segregatora i dla nadzoru:
  dziennik sprawdzeń jest solidnym dowodem, ale nikt nie przedkłada
  pliku JSON Lines.

  **Nowe są przy tym dwie liczby**, których dotychczas nigdzie nie było
  widać: *średnia pewność* – jak pewne było rozpoznawanie przy tym, co
  znalazło – i *wskaźnik maskowania*, udział zastąpionych znaków w
  tekście. Oba stoją ze swoją granicą: pewność **nic** nie mówi o
  przeoczonym, a obok niej stoi zawsze, ile trafień w ogóle obejmuje;
  wskaźnik nie liczy obrazów i przy dokumencie z ilustracjami wypada za
  wysoko.

  **Wartości znalezione nie stoją na kartce** – ta sama granica co przy
  dzienniku i przebiegu wyszukiwania. Na dole stoją dwa wiersze, które
  nie mówią tego samego: suma kontrolna pokazuje, że kartka jest
  niezmieniona; wiersz dziennika – tylko przy działającym dzienniku –
  odsyła do **podpisanego** wiersza, który dokumentuje przebieg. Dopiero
  on dowodzi pochodzenia.

- **„Jak pewne to było?” – wskaźniki przy wyniku.** Przycisk
  „Wskaźniki” pod wynikiem rozwija to, czego dotychczas nigdzie nie
  było widać: miejsca znalezienia, słowa i znaki, rozkład dla każdego
  rodzaju jako wiersz słupkowy, do tego średnią pewność i wskaźnik
  maskowania. Te same liczby co w raporcie sprawdzenia, tylko od razu i
  bez druku.

  **Z zastrzeżeniem w tej samej powierzchni:** obok pewności stoi, ile
  trafień obejmuje, a pod nią zdanie, że **nic** nie mówi o przeoczonym.
  Procent bez tego zdania czyta się jak wskaźnik trafień – a kto tak go
  rozumie, jest gorzej niż bez tej liczby.

  Liczone jest dopiero przy rozwinięciu: mianownik wskaźnika maskowania
  kosztuje na plik jeden odczyt, a nie ma go płacić ten, kto w ogóle nie
  patrzy na liczby.

- **Budowanie własnych wzorców wyszukiwania bez pisania jednego.**
  Zakładka „Własne wzorce wyszukiwania” prowadzi teraz w trzech krokach
  przez sprawę: *Czego Państwo szukają? → Jak wygląda taka dana u
  Państwa? → Nazwać i zapisać.* Wpisują Państwo przykład – np.
  `KD-004711` – program wyprowadza z niego regułę i pisze słowami, czego
  ona szuka. Podgląd z licznikiem trafień sprawdza przy każdym
  naciśnięciu klawisza.

  **Wyrażenie regularne w ogóle się nie pojawia.** Umiejętność nigdy nie
  była problemem: własne wzorce wyszukiwania istnieją od dawna, tylko
  wymagały wyrażenia jak `\bKD-\d{6}\b`, a takiego w kancelarii czy
  dziale kadr nikt nie napisze. Kto *chce* je napisać, rozwija tryb
  eksperta.

  **Katalog wzorców jest na nowo posortowany:** trzynaście kart z nazwą,
  wyjaśnieniem i przykładową wartością, filtrowanych przez znaczniki
  kategorii – finanse, urzędy, kontakt, personel, medycyna.

  A gdy wyprowadzony wzorzec chwyta zbyt szeroko, program mówi to sam z
  siebie: przykład z samych cyfr trafia każdy rok i każdą kwotę, a kto
  nie umie czytać wyrażenia, inaczej by tego nie zauważył.

- **Siedem znaczników zamiast pięćdziesięciu sześciu haczyków.** Nowa
  zakładka „Co jest szukane” zbiera wszystkie rozpoznawalne rodzaje w
  siedem grup – osoba, kontakt i miejscowość, identyfikatory, finanse,
  technika, kategorie szczególne, firmy i własne. Znacznik przełącza
  swoją grupę, „Wszystko włączone” i „Wszystko wyłączone” całą listę; pod
  spodem każdy rodzaj pozostaje pojedynczo zaznaczalny.

  **Domyślnie wszystko włączone, i tak pozostaje.** To, co tu jest
  wyłączane, w ogóle nie jest szukane – najgrubsza ingerencja, na jaką
  pozwala okno reguł, i działa na każdy dokument. Dlatego pod listą
  zawsze stoi, ile rodzajów jest wyłączonych, a zapisywane jest tylko
  wyłączone: nowy rodzaj jest przez to obecny też w pliku reguł
  sprzed dwóch dni, zamiast po cichu wypaść.

- **Przenieść ramkę na wszystkie strony.** W oknie poprawek przycisk
  **Zastosuj do wszystkich stron** bierze ostatnio wyciągniętą ramkę i
  zaciemnia to samo miejsce na każdej kolejnej stronie – dla nagłówka
  firmowego, stopki i pola sygnatury akt. Przy zeskanowanych aktach z
  osiemdziesięcioma stronami robi to z dwudziestu minut dwie.

  **„To samo miejsce” oznacza to samo *względne* miejsce na kartce.** W
  stosie z podajnika regularnie leży strona w poprzek, inna to A3,
  trzecia obrócona; bezwzględnie przeniesiony prostokąt lądowałby tam
  obok nagłówka firmowego – i widziałoby się pas, i uważało sprawę za
  załatwioną.

  **Zaciemniane jest, nie zastępowane**, nawet jeśli ramka wyjściowa
  była zastępnikiem: pod tym samym prostokątem na stronie czterdziestej
  stoi coś innego niż na pierwszej, a zastępnik z tym samym numerem
  twierdziłby o równości, której nie ma.

- **Adnotacja na pasie zaciemniającym.** W prawie wglądu do akt stoi
  obok każdego zaciemnienia, dlaczego zaciemniono. Nowe pole
  **Adnotacja na pasie** w ustawieniach – lub `--balkenvermerk` – pisze
  krótki tekst na każdym pasie: „§ 203 KK”, „RODO”, „poufne”. Dla
  dokumentu wydawanego przez urząd to różnica: odbiorca widzi powód, bez
  posiadania protokołu, którego i tak nigdy nie dostanie.

  **Domyślnie puste**, bo adnotacja jest w wydanym dokumencie widoczna i
  sama jest daną – mówi odbiorcy, pod jakim tytułem coś jest
  wstrzymywane. Działa tylko przy **zaciemnianiu**; tam gdzie stoi
  zastępnik, nie ma pasa. Na pasie za małym na czytelny tekst odpada –
  nieczytelna adnotacja wygląda jak błąd.

- **Odblokowanie bez połączenia z internetem – teraz kompletne.** W
  oknie licencji „Odblokuj bez internetu” istniało już od dawna: na
  górze kod żądania do zabrania, na dole pole dla odblokowania, które
  wraca. Tylko dotychczas nikt nie mógł go **wystawić** – narzędzie do
  tego brakowało, a kod szedł w próżnię. To jest naprawione.

  Dla urzędów i kancelarii z odizolowanymi komputerami to nie przypadek
  szczególny, tylko normalny – i to dokładnie grupa docelowa, u której
  obietnica „Państwa dokumenty nigdy nie opuszczają komputera” waży
  najciężej. Kod nic nie zdradza o dokumentach: zawiera identyfikator
  licencji i wartość skrótu komputera, nic poza tym.

- **Pobrać ze skanera.** „Plik → Pobierz ze skanera …” wczytuje stos
  bezpośrednio i kładzie strony na liście – dla kancelarii pocztowej
  różnica między dwoma krokami roboczymi a jednym. Podajnik jest
  opróżniany do ostatniej strony; urządzenie, rozdzielczość i kolor
  wybiera systemowe okno dialogowe skanera, które Państwo i tak znają.

  **Nie jest oczyszczane samo z siebie.** Widzą Państwo najpierw, co
  weszło, i naciskają potem „Oczyść” jak przy każdym innym pliku – skan
  przechodzący od razu odebrałby Państwu spojrzenie na krzywo wciągnięty
  stos.

  **Jest to dostępne tylko pod Windows**, i punkt menu mówi to też na
  Macu: tam oprogramowanie Państwa skanera pisze do folderu, a „Obserwuj
  folder …” oczyszcza wszystko, co tam ląduje.

### Inne

- **Lista wszystkich znajdowanych danych jest teraz dołączona** i
  tworzona z kodu źródłowego (`hilfe/GEFUNDENE-ANGABEN.md`): 177
  rodzajów w 35 krajach, 23 z nich z obliczeniem cyfry kontrolnej.
  Podaje też, jak liczono – liczymy `[NAZWISKO]` raz, tam gdzie inni
  prowadzą imię, drugie imię i nazwisko jako trzy wpisy.

- **Zaciemnianie jest teraz też w Word, PowerPoint, OpenDocument i
  HTML.** Wybór między zastępnikiem a zaciemnieniem był dotychczas
  tylko dla plików PDF. Teraz potrafią to też pozostałe: znalezisko jest
  usuwane, a w jego miejscu stoi czarny pas – w samym dokumencie, nie
  jako obraz nad nim. Kto przekazuje plik dalej, wydaje zaciemnione
  akta, nie takie, w których zaciemnione wciąż leży pod spodem jako
  tekst.

  **Decyduje się o tym osobno**, w dwóch polach wyboru: „Przy PDF” i
  „Przy Word, PowerPoint, OpenDocument i HTML”. Chce się tego różnie –
  zaciemniony PDF idzie do urzędu, ta sama sprawa jako plik Word wędruje
  dalej po firmie i ma pozostać czytelna. W wierszu poleceń odpowiednio
  `--pdf-modus` i `--office-modus`; zapisane „Zaciemniaj” z
  wcześniejszych wydań obowiązuje dalej dla PDF.

  W arkuszach, czystym tekście, CSV i e-mailu pas nie działa – tam
  brakuje powierzchni, na której mógłby leżeć. Nadal wstawiany jest
  zastępnik, a wynik **mówi to teraz**, zamiast robić to po cichu.

- **Nowość: „Usuń” – miejsce znalezienia po prostu pozostaje puste.**
  Trzeci tryb działania obok zastępnika i zaciemnienia, i jedyny
  potrafiący **każdy** format: pominięcie czegoś nie potrzebuje
  powierzchni. W PDF nic przy tym nie jest rysowane, w Word i HTML
  miejsce pozostaje puste, w tabeli podobnie.

  Jest najcichszym z trzech: kto czyta wynik, nie widzi, że coś tam
  kiedyś stało – nawet długość wartości się już nie zdradza. Dla pisma,
  które ktoś ma sprawdzić, zastępnik pozostaje zwykle lepszym wyborem.

  W obrazach żadna z trzech opcji nie obowiązuje: pikseli nie da się
  zastąpić zastępnikiem ani pominąć. To, co rozpoznawanie tekstu tam
  znajduje, jest jak dotychczas zawsze zamalowywane.

- **Okno poprawek nie twierdzi już o zastąpieniach, których nie ma.** Po
  prawej stronie stał przy każdej wartości zastępnik – także przy pliku
  zaciemnionym, w którym ani jeden nie występuje. Kliknięcie w taki
  wiersz nic nie zaznaczało, a „Cofnij” szło w próżnię. Teraz stoi tam
  „zaciemnione” lub „usunięte”, a wierszy w ogóle nie da się cofnąć:
  tekst zniknął, nie ma nic do przywrócenia. Dotyczyło to zaciemnionych
  plików PDF, Word i OpenDocument oraz wszystkiego znalezionego w
  obrazach.

- **Widok tekstu pokazuje teraz pasy jako pasy.** Zaciemniony plik Word
  wyglądał przy poprawianiu **pusto**: w zaciemnionych miejscach stały
  luki, jakby program połknął tekst. Powodem był widok, nie wynik – w
  samym dokumencie pas leżał cały czas prawidłowo. Teraz stoi też w
  widoku tam, czarny jak w wyniku, w Word, PowerPoint, OpenDocument i
  HTML.

- **Wiadomości Outlook (`.msg`) są teraz oczyszczane.** `.eml` był od
  dawna – w niemieckich firmach jednak Outlook jest e-mailem, a tam
  zapisana wiadomość nazywa się `.msg`. Dzięki temu najgęstszy format
  PII jest objęty też w swojej najpopularniejszej formie odkładania:
  temat, nadawca, wiersze odbiorcy, treść wiadomości, wersja HTML, lista
  odbiorców i załączniki – te ostatnie istniejącymi drogami i tymi
  samymi zastępnikami co tekst maila.

  **Plik `.msg` niesie ten sam tekst wielokrotnie**, i to jest pułapka:
  jako czysty tekst, jako HTML **i** jako RTF. Kto oczyszcza tylko czysty
  tekst, nic nie zrobił – Outlook pokazuje preferencyjnie RTF. Wersja
  RTF jest dlatego usuwana całkowicie, podobnie jak nagłówki internetowe
  z ich łańcuchem Received i binarne klucze wyszukiwania, które
  przetrwają każde oczyszczanie tekstu. Wynik nadal otwiera się w
  Outlook i pokazuje tekst bez wyróżnienia czcionką; raport mówi to
  wyraźnie.

- **Opisywać reguły własnymi słowami, zamiast pisać wyrażenie
  regularne.** Okno reguł potrafi dużo i wymagało do tego wzorca
  wyrażenia regularnego – miejsca, na którym większość się zatrzymuje.
  Teraz wystarczy zdanie: „Nasze sygnatury akt formy 12 C 345/26 mają
  pozostać.” Poziom SI proponuje z tego pojęcia i wzorce wyszukiwania.

  **Przejmowane jest tylko to, co Państwo zaznaczą – a domyślnie nic nie
  jest zaznaczone.** Przy każdej propozycji stoi zdanie, co ona oznacza,
  i liczba jej trafień w przykładowym tekście, który Państwo mogą
  dołączyć. To, co ochronę **odbiera**, jest jako takie oznaczone: „to
  pojęcie zawsze usuwaj” i „to pojęcie nigdy nie usuwaj” wyglądałyby na
  liście inaczej takie same. Propozycje pasujące do wszystkiego w ogóle
  nie są pokazywane.

- **Dziennik sprawdzeń liczy teraz zbiorczo przez wszystkie
  stanowiska.** Jeśli firma kładzie dzienniki przez `protokoll_pfad” na
  udostępniony zasób, każde stanowisko pisze tam swój własny plik
  miesięczny – dotychczas inspektor ochrony danych z trzydziestoma
  stanowiskami musiał oglądać trzydzieści plików osobno. Nad listą stoi
  teraz wiersz z sumami miesiąca, i **zgłasza przerwane łańcuchy z
  nazwą**: późniejsza zmiana rzuca się w oczy tylko wtedy, gdy ktoś
  sprawdza, a w trzydziestu plikach nikt nie sprawdza ręcznie.

  **Żadnego zestawienia na osobę** – także nie w tym widoku. Ranking
  „kto ile oczyścił” nadawałby się do kontroli zachowania i wydajności,
  a w prawie współdecydowania liczy się to, nie zamiar. Liczone są
  przebiegi, pliki i trafienia w skali firmy.

- **„Zaproponuj profil z pisma”: zapytać reguły raz zamiast przechodzić
  czterdzieści cztery rodzaje.** W oknie reguł jest nowy przycisk:
  pokazuje poziomowi SI pismo, ustala, o co chodzi – list lekarski,
  aplikacja, umowa, faktura, decyzja – i proponuje pasujące strategie.
  Przy liście lekarskim daty są np. przesuwane zamiast zastępowane, bo w
  dokumentacji medycznej treścią jest chronologia.

  **Profile stoją w programie, model tylko wybiera** – reguły
  zaciemniania nie zależą od tego, co model językowy uważa za dobry
  pomysł. Proponowany jest każdy punkt osobno i z uzasadnieniem;
  przejmowane jest nic bez pytania, a to, co Państwo sami ustalili,
  pozostaje nienaruszone. Bez poziomu SI pozostaje bezpieczna wartość
  domyślna: zastępnik dla wszystkiego.

- **Nowa strategia „wymyśl”: wiarygodna fałszywa wartość zamiast
  zastępnika.** „Pani Berger napisała do Pana Dopplera w Fuldzie” zamiast
  „[NAZWISKO_1] napisał(a) do [NAZWISKO_2] w [MIEJSCE_1]” – dla
  materiałów szkoleniowych, akt pokazowych, zbiorów danych testowych i
  wszystkiego, co potem trafia przed SI. Forma grzecznościowa, budowa
  zdania i czytelność pozostają zachowane.

  Ta sama wartość dostaje tę samą fałszywą wartość, przez wszystkie
  pliki procesu i na każdym komputerze z tym samym plikiem reguł – **bez
  zapisywania nigdzie przyporządkowania** (ten sam mechanizm co przy
  funkcji skrótu). Adresy e-mail leżą na zarezerwowanych domenach
  przykładowych, numery telefonu w zarezerwowanym do tego zakresie,
  wymyślone IBAN-y niosą prawidłowo obliczoną cyfrę kontrolną. Możliwe
  dla nazwisk, miejscowości, adresów, firm, e-mail, telefonu i IBAN; dla
  innych rodzajów reguła jest odrzucana, zamiast pozostać bezskuteczna.

  **Raport wyraźnie mówi, że wymyślono.** Tak oczyszczony dokument czyta
  się jak prawdziwy i nim nie jest – nie nadaje się jako dowód i nie
  wolno go przekazywać jako oryginał.

- **Kontrsprawdzenie: „Kto pozostaje rozpoznawalny?”** Nowy znacznik pod
  poziomem SI przedkłada **gotowy wynik** jeszcze raz modelowi
  językowemu i pyta, kto mimo oczyszczenia jest do rozpoznania. Chodzi o
  przypadek, którego żadne rozpoznawanie świata nie znajduje, bo w ogóle
  nie stoi tam żadne nazwisko: „jedyna położna w powiecie”, „kolega,
  który zwolnił się w marcu po pożarze”. Żaden wzorzec nie chwyta, a na
  miejscu i tak każdy wie, o kogo chodzi.

  **Nic przy tym nie jest usuwane.** Miejsca stoją ze zdaniem
  uzasadnienia w raporcie, a decyduje się ręcznie – program samodzielnie
  biorący zdania z pisma, bo wydają mu się zdradliwe, robi z
  oczyszczenia parafrazę, i nikt nie widziałby, czego brakuje. Najwyżej
  pięć miejsc na plik; to, czego model nie może udokumentować dosłownie,
  odpada. W wierszu poleceń: `--restrisiko` razem z `--ki`.

- **Droga powrotna z SI: „Przetłumacz odpowiedź z powrotem”.** Dotychczas
  zbudowana była tylko połowa pętli – skopiować tekst, wkleić
  oczyszczony, przedłożyć SI. Odpowiedź wracała z `[NAZWISKO_1]`, a kto
  jej potrzebował, wpisywał ręcznie z powrotem to, co ręcznie wyjął.
  Teraz droga powrotna stoi w menu „Program”: skopiować odpowiedź,
  kliknąć wpis, prawdziwe nazwiska stoją znów tam.

  Przyporządkowanie do tego leży **tylko w pamięci roboczej**, obowiązuje
  zawsze tylko dla ostatnio oczyszczonego miejsca i wygasa po godzinie;
  kto wyłącza strażnika schowka, od razu je traci. Przywrócić da się
  przy tym tylko to, co zostało zastąpione – zaciemnione, zamaskowane i
  zahashowane nie da się odwrócić, a program mówi, ile miejsc musiał
  dlatego pozostawić. Zarządzane instalacje wyłączają drogę powrotną w
  całości przez wytyczną `rueckweg`.

- **Obserwuj folder: to, co jest wkładane, leży wkrótce potem oczyszczone
  na wyjściu.** Dla kancelarii pocztowej, zespołu skrzynki pocztowej lub
  folderu skanów – raz skonfigurować, potem nikt już nie klika. Do
  znalezienia pod „Plik → Obserwuj folder …”, w wierszu poleceń przez
  `--wache <folder>`.

  Oryginał pozostaje tam, gdzie leżał; na życzenie wędruje niezmieniony
  do podfolderu „Zrobione”, przy czym nigdy nic nie jest nadpisywane.
  Plik jest dotykany dopiero, gdy jest w pełni zapisany – plik jeszcze
  kopiowany przez sieć byłby inaczej odczytany w połowie i zgłoszony
  jako oczyszczony. To, co pójdzie nie tak, pozostaje leżeć i jest
  zgłaszane, zamiast być powtarzane w nieskończoność. A obserwacja
  pamięta zrobione bez nazwy pliku: to, co leży w folderze wejściowym,
  często zdradza już w nazwie, o co chodzi.

  **Obserwacja folderu poza własnym profilem użytkownika – np. na
  dysku sieciowym – wymaga licencji automatyzacji.** Folder, do którego
  ma dostęp kilka osób, jest usługą, nie stanowiskiem pracy; we własnym
  profilu i w okresie testowym to ograniczenie nie obowiązuje.

### Naprawione

- **Ustawienia były obcięte po prawej stronie.** Okno otwierało się ze
  stałym rozmiarem, a ten wystarczał tylko dla rozmiaru czcionki, przy
  którym było rozwijane: na Macu „Sprawdź teraz”, „Zmień …” i wskazówki
  obok stały w połowie poza ekranem. Teraz otwiera się tak szeroko, jak
  potrzebują tego jego strony – w każdym języku i przy każdym rozmiarze
  czcionki, ograniczone tylko ekranem.

- **„Sprawdź teraz” odpowiada teraz widocznie.** Wynik stał w wierszu
  stanu okna głównego – więc za oknem ustawień, z którego zapytano. Kto
  sprawdzał, nic nie widział. Teraz odpowiedź przychodzi jako komunikat
  nad ustawieniami, a jeśli dostępna jest nowa wersja, od razu prowadzi
  do instalacji. Przy starcie programu pozostaje jak dotychczas przy
  wierszu stanu, bez pytania żadne okno się nie otwiera.

- **Skopiowane pliki nie docierały na Macu do schowka.** Odkładanie
  oczyszczonych plików zgłaszało sukces, a mimo to nic użytecznego nie
  odkładało – wklejenie nic nie dawało. Dotyczyło wszystkiego, co pisze
  pliki do schowka.

- **A ze schowka na Macu był czytany tylko pierwszy plik.** Kto
  skopiował trzy pliki w Finderze i wybrał „Oczyść schowek teraz”,
  dostawał dwa z nich nieoczyszczone z powrotem – bez żeby cokolwiek to
  powiedziało. Teraz przychodzą wszystkie.

- **„Sprawdź plik” przyjmuje teraz też przeciągnięte pliki** – jak okno
  główne. Odłożone dochodzi, zamiast odrzucać dotychczasowy wybór; to
  samo odłożone dwa razy niczego nie zmienia, a czego program nie potrafi
  przeczytać, jest zgłaszane, zamiast połykane.

- **A okno mówi, że czeka na Państwa.** Otwierało się z pustym polem i
  szarym przyciskiem „Sprawdź” – to wygląda, jakby niczego tam nie było,
  nie jakby brakowało wyboru. Teraz stoi tam „Jeszcze nie wybrano pliku –
  proszę przeciągnąć tutaj lub wybrać poniżej przez ‚Wybierz pliki …’.”

- **Długi przebieg mówi teraz, że działa.** „Wczytywanie modelu
  dodatkowego dla dokładniejszego rozpoznawania – chwileczkę …”
  pozostawało tam, dopóki rozpoznawanie liczyło: przy pliku z 47 500
  słowami więc osiemnaście minut, mimo że ładowanie skończyło się po
  dziewięciu sekundach. Kto to widzi, uważa program za zawieszony. Teraz
  po tym następuje „Trwa dokładniejsze rozpoznawanie – przy długich
  tekstach trwa to kilka minut”, a wiersz stanu liczy: „Dokładniejsze
  rozpoznawanie (7/312)”. Zgłaszane jest przy tym z pętli modelu – co 250
  słów, więc mniej więcej co sześć sekund – nie na blok tekstu: blok
  tekstu niesie dwanaście tysięcy słów i potrzebuje minut.

- **Przerwany przebieg mówi teraz, że został przerwany.** Kto naciskał
  „Anuluj”, czytał potem „0 z 1 pliku(ów) oczyszczonych.” – policzone
  poprawnie, a mimo to błędna informacja. Komunikat o tym, który plik był
  dotknięty, był w tym samym momencie nadpisywany przez komunikat
  liczący. A na liście plików stało dalej „działa …”, mimo że nic już nie
  działało; stoi tam teraz „przerwane”.

- **Zdanie o ochronie danych było obcięte.** „… żadnej chmury, żadnego
  przesyłania. Więcej w ochr” – przy szerokości okna, z jaką program
  startuje, kończyło się w środku słowa. Zajmuje teraz pełną szerokość.

- **Usługa licencji mogła coś zakomunikować, i nikt nie słuchał.** Gdy
  wszystkie miejsca licencji są zajęte, licencja wygasła, klucz nieznany
  lub zarządzanie licencjami u dostawcy wyłączone, usługa wysyła
  dokładnie na to powód – przewidziane od początku było, że dostaną go
  Państwo wyjaśniony **raz**. Nigdy nie był pokazywany. Teraz pojawia się
  wskazówka mówiąca najpierw, że program działa dalej bez zmian, a potem
  o co chodzi. Raz na powód: kto go odklikał, nie widzi go ponownie przy
  codziennym sprawdzeniu – ale widzi, gdy powód się zmienia.

- **Licencja wieloosobowa kupiona w sklepie pokazywała „1 miejsce”.**
  Sklep rozdziela przygotowane klucze i sam trzyma zakupioną liczbę
  miejsc; pokazywana była jednak liczba z samego klucza, a ta przy
  każdym kluczu zapasowym brzmi na jedno miejsce. Kto kupił osiem
  miejsc, czytał „1 miejsce” – a od drugiego zalogowanego komputera
  wyświetlacz stał na czerwono wraz z „Proszę skontaktować się z
  zarządem”. Teraz obowiązuje liczba ostatnio zgłoszona przez usługę;
  bez odpowiedzi pozostaje przy kluczu, a mniejsza niż zakupiony zakres
  nigdy nie będzie. To samo dotyczy dokupień i przedłużeń: zmieniają u
  dostawcy liczbę miejsc, nie Państwa klucz.

- **Po zakupie stało „Licencjonowane dla Maskuro Licencja prywatna”.**
  To nie jest nazwisko, tylko zastępnik, pod którym klucze są
  przygotowywane – Państwa nazwisko nie może tam stać, bo klucz jest
  podpisywany już przed zakupem. Zamiast pokazywać Państwu obce nazwisko
  jako Państwa, stoi tam teraz po prostu „Licencja prywatna” i liczba
  miejsc. Przy licencji wystawionej na Państwa nazwisko stoi tam bez
  zmian Państwa nazwisko.

- **W menu Pomoc stało „Pomoc _FAQ”.** Znak „i” zamienił się w
  podkreślenie, ponieważ Qt czytał go jako oznaczenie litery klawisza.
  Teraz stoi tam „Pomoc i FAQ”.

- **Okno ustawień pozostawało, gdy program chował się do ikony** – i
  nawet wtedy, gdy okno główne było zamknięte. Teraz chowa się razem.
  (Dotyczy tylko tego wydania; własne okno jest nowe.)

- **Odrzucone zapytanie o licencję mówi teraz, na czym to polega.**
  Jeśli usługa licencji odrzucała zapytanie bez podania powodu, w oknie
  licencji stało na czerwono „Nieznana odpowiedź.” – zdanie, z którym
  ani Państwo, ani wsparcie nic nie mogą zrobić, i które każe Państwu
  szukać błędu w swoim kluczu. Teraz stoi tam, co faktycznie się stało:
  że usługa odrzuciła bez uzasadnienia, i do kogo się zwrócić. Jeśli
  zarządzanie licencjami u dostawcy jest tymczasowo wyłączone, jest to
  też nazwane – wraz ze wskazówką, że Państwa klucz tym nie jest
  dotknięty.

- **Na Macu skonfigurowane języki nagle liczyły się jako brakujące.**
  Przy starcie program zgłaszał „Nie jest zainstalowany żaden model
  językowy” i oferował konfigurację początkową, mimo że języki były
  dawno wczytane – kto sprawdzał pod „Języki dokumentów”, znajdował je
  tam w komplecie. Program szukał ich, zależnie od drogi startu, w dwóch
  różnych miejscach: uruchomiony z folderu Programy, znajdował je;
  uruchomiony jako ta sama budowa w postaci zwykłego folderu, szukał ich
  obok siebie, gdzie żadnych nie ma. Od teraz na Macu obowiązuje bez
  wyjątku to samo miejsce w profilu użytkownika, bez względu na to, jak
  program jest zapakowany. Nic nie musi być wczytywane na nowo.

- **„Co nowego” pokazywało połowę listy.** Okno po aktualizacji urywało
  się w środku zdania, a pozostałe punkty stały jako puste znaczniki
  wyliczenia. Winny był zastępnik w ostrych nawiasach – np.
  `<plik>.docx` – który wyświetlacz uważał za wyróżnienie i od tego
  miejsca odrzucał wszystko dalej. Akurat nowości bezpieczeństwa były
  tym dotknięte. Pomoc pokazuje takie zastępniki od zawsze poprawnie; to
  okno robi to teraz też.

- **Uszczypnięcie dwoma palcami powiększa teraz w oknie poprawek.** Na
  gładziku to *ta* gesta powiększania – w edytorze dotychczas nic nie
  robiła, a kto chciał obejrzeć miejsce dokładniej, musiał sięgnąć po
  suwak lub Ctrl+kółko myszy. Strona podąża natychmiast za gestem i przy
  puszczeniu jest znów rysowana ostro.

- **Powiększane jest miejsce, na które się patrzy.** Uszczypnięcie
  powiększa wokół punktu między palcami, Ctrl+kółko myszy wokół punktu
  pod kursorem. Przyciski, skróty klawiszowe i suwak powiększenia
  trzymają środek – nie należy do nich miejsce, na które się wskazuje.
  Wcześniej przy wszystkich pozostawała tylko wartość przewinięcia: od
  dopasowanej strony trzymało to górną krawędź, a wszystko poniżej
  wędrowało przy powiększaniu poza obraz.

- **„Przed/po” było w podglądzie strony martwym przyciskiem.** Dopóki
  podgląd strony był włączony, dawał się nacisnąć – i za każdym razem
  zgłaszał, że oryginału nie da się otworzyć. Nie ma tam też niczego do
  porównania: podgląd strony jest odwzorowaniem oczyszczonej wersji,
  odpowiednika oryginału nie ma. Przycisk jest teraz zablokowany i przy
  najechaniu podaje powód wraz z wyjściem (widok tekstu). Jego opis
  obiecywał ponadto wyraźnie, że porównanie działa „niezależnie od tego,
  czy aktywny jest widok tekstu czy strony” – to nigdy nie było prawdą.

- **Podgląd strony powodował awarię LibreOffice.** Jeśli dwa podglądy
  strony powstawały jednocześnie – np. „Zaciemnij jako PDF” podczas gdy
  podgląd jeszcze liczył – system zgłaszał awarię LibreOffice, mimo że
  strony na końcu i tak się pojawiały: oba przebiegi sięgały do tego
  samego roboczego składowiska LibreOffice, czego ono nie znosi. Teraz
  dostaje je zawsze tylko jeden przebieg; pozostałe uciekają do
  własnego. Potrzebują na to kilka sekund dłużej, za to nie ma już
  komunikatu błędu, i żaden z przebiegów nie pozostaje bez wyniku. Drugie
  zlecenie renderowania obok już działającego w ogóle nie jest
  przyjmowane.

- **„Pokaż oryginał” mogło zakończyć program.** Jeśli oryginału nie dało
  się otworzyć – bo został przeniesiony, przemianowany, zabezpieczony
  hasłem lub leży na odłączonym dysku – okno poprawek przerywało się bez
  ostrzeżenia, a otwarte kopie robocze przepadały. Teraz pojawia się
  wskazówka, przełącznik wraca, a oczyszczona wersja pozostaje. Tam
  gdzie oryginał zasadniczo nie pasuje – np. przy podglądzie strony PDF
  powstałym z pliku Word – przełącznik jest z góry zablokowany i przy
  najechaniu podaje powód, zamiast pokazywać przy każdym naciśnięciu tę
  samą wskazówkę.

- **Zgłoszenia błędów nigdy nie docierały.** Kto chciał zgłosić błąd,
  dostawał „Strona przeciwna odrzuciła zgłoszenie” – i nikt go nigdy nie
  widział. Dwie przyczyny, obie po drodze: program nie identyfikował się
  wobec serwera i był przez to odrzucany przez ochronę przed masowym
  dostępem, a adres wskazywał na drugą nazwę, za którą program nie
  podążał. Oba naprawione; zgłoszenie znów wychodzi. **To samo dotyczyło
  odblokowania licencji**: logowanie, wylogowanie i zapytania też nie
  docierały do usługi – tam tylko niepozornie, bo nieodpowiedziane
  zapytanie celowo niczego nie zmienia w Państwa licencji. A jeśli
  odmowa mimo to pozostaje niewyjaśniona, stoi teraz przy niej jej
  techniczny numer, zamiast żeby każda przyczyna wyglądała tak samo.

- **Kliknięcie w „Pokaż oryginał” mogło zakończyć program.** Jeśli
  oryginału nie dało się otworzyć – przeniesiony, przemianowany, na
  odłączonym dysku sieciowym, zabezpieczony hasłem lub uszkodzony –
  okno poprawek znikało wraz ze wszystkimi otwartymi kopiami roboczymi.
  Teraz przełącznik pozostaje przy oczyszczonej wersji, a pole mówi, co
  się dzieje; techniczny powód stoi w szczegółach, gdyby chcieli go
  Państwo zgłosić. To samo dotyczy wyniku, którego nie da się wyświetlić:
  okno otwiera się i mówi to, zamiast znikać.

- **Pytanie o awarię przychodziło za często – i kasowało ślad, o który
  pytało.** Pojawiało się też wtedy, gdy nic się nie zawiesiło: wpis
  powstaje, gdy tylko gdzieś wystąpi nieoczekiwane zakłócenie, nawet gdy
  program je przetrwa i potem zwyczajnie się kończy; nigdy nie był
  sprzątany. A kto odpowiadał „Nie”, niszczył jedyne szczegóły
  zdarzenia – wpis znikał już przy *wyświetleniu* pytania. Oba
  naprawione: uporządkowane zakończenie sprząta wpis, pytane jest tylko
  o prawdziwe przerwanie, a odhaczane jest dopiero po Państwa odpowiedzi.
  Szczegóły i tak stoją w dzienniku błędów na własnym komputerze; kto nie
  chce niczego wysyłać, mimo to niczego nie traci. Wysyłane jest nadal
  tylko to, co Państwo wcześniej w pełni zobaczyli i sami zwolnili.

- **„Oczyść” mogło pozostać niemo zablokowane.** Jeśli modele językowe
  zawisały przy wczytywaniu, przycisk pozostawał wyłączony – bez
  wyjaśnienia. Kliknięcie nic nie robiło, a wiersz stanu mówił nadal
  „Wczytywanie modeli językowych …”, nawet po dziesięciu minutach.
  Przyczyna: zakłócenia w procesach tła szły do miejsca, którego nikt nie
  widzi przy starcie z menedżera plików; pozostawało okno wyglądające na
  gotowe do pracy i nieodpowiadające na żadne kliknięcie. Teraz takie
  zakłócenia lądują w dzienniku błędów, wczytywanie modeli językowych w
  każdym przypadku zgłasza swoją porażkę zamiast po cichu poddawać się,
  a jeśli mimo to pozostaje ciche, aplikacja po trzech czwartych minuty
  mówi, że coś jest nie tak, z radą w szczegółach. Zablokowany przycisk
  podaje przy najechaniu swój powód. Długie pierwsze doładowanie nie
  liczy się przy tym jako cisza: dopóki zgłaszany jest postęp, pozostaje
  spokojnie. Awarią nie liczy się to wszystko: aplikacja działa dalej, i
  przy następnym starcie o to nie pyta.

- **Na Macu program nie znajdował już aktualizacji – i mówił, że jest
  aktualny.** Wersja Mac nie niosła ze sobą katalogu certyfikatów
  głównych; szukała go w miejscu istniejącym tylko na komputerze, na
  którym jest budowana. Przez to nie mogła u żadnego serwera sprawdzić,
  z kim rozmawia, i przerywała każde połączenie: żadnych aktualizacji,
  żadnego odblokowania licencji, żadnego doładowania modeli językowych,
  żadnego zgłoszenia błędu. Starsze wersje robiły z tego po cichu
  informację „Używają Państwo najnowszej wersji”. Certyfikaty leżą teraz
  w samym programie; jeśli tam żadnych nie znajdzie, bierze systemowe, a
  na Macu w ostateczności z pęku kluczy – a jeśli w ogóle żadnych nie
  ma, mówi to, zamiast twierdzić o najnowszej wersji. Samo sprawdzenie
  nigdy nie jest przy tym wyłączane.

  Tę jedną aktualizację użytkownicy Mac muszą jeszcze zainstalować
  ręcznie: wersja nieosiągająca serwera nie może się też sama odnowić.

### Zmienione

- **Okno główne zostało uporządkowane.** Na dole stało sześć przycisków
  tej samej wielkości obok siebie – „O …”, „Instrukcja” i „Pomoc i FAQ”
  pod spodem, mimo że te same trzy drogi stały już w menu Pomoc powyżej.
  Są teraz połączone w jeden przycisk „Pomoc”, który je rozwija; żaden
  nie ginie. Na dole pozostają dwie drogi, którymi się naprawdę zaczyna:
  „Oczyść” i „Zaciemnij ręcznie …”.

- **To, co program właśnie robi, stoi teraz w stałym miejscu.** Komunikat
  („Wczytywanie modeli językowych …”, „(3 / 7) pismo.pdf”, „5 z 7
  pliku(ów) oczyszczonych.”) wisiał dotychczas jako szary tekst między
  dwoma rzędami przycisków. Dostał własną powierzchnię, z kolorową
  kropką przed nim: szara, dopóki nic się nie dzieje, niebieska podczas
  pracy, zielona po gładkim przebiegu i żółta, gdy pojawiły się
  wskazówki. Kropka nie mówi nic, czego nie ma obok – mówi to tylko
  szybciej.

- **Ustawienia stały się własnym oknem.** Leżały dotychczas w oknie
  głównym – pole z czterema zakładkami, rozwijane pod „Więcej ustawień”,
  które potem było za małe na swoją treść: zawsze stał w nim pasek
  przewijania, a wybór między anonimizowaniem a pseudonimizowaniem stał
  w połowie poza obrazem. Przycisk nazywa się teraz „Ustawienia …” i
  otwiera okno z panelem bocznym; każda z czterech stron mieści się w
  całości. Okno główne nie skacze już przy otwieraniu, a listę plików
  można widzieć obok.
  Zmieniło się tylko, gdzie stoją ustawienia – jakie są i co robią, jest
  bez zmian.

- **„Szczegóły” rozwija się, zamiast skakać.** Okno rosło dotychczas w
  jednym obrazie, i trzeba było potem szukać, co się zmieniło. Teraz
  porusza się tam.

- **Rozmiary czcionek i odstępy podążają w całym oknie za tą samą
  miarą.** Nagłówki były w dwóch miejscach różnej wielkości, a wiersze
  tej samej rangi stały w różnych odstępach. Widoczne jest to jako
  spokój, nie jako pojedyncza zmiana.

- **Anonimizowanie jest teraz wartością domyślną.** Dotychczas domyślnie
  było pseudonimizowanie: te same osoby dostawały ten sam numer
  (`[NAZWISKO_1]`, `[NAZWISKO_2]`), odniesienia pozostawały czytelne –
  prawnie pozostawały przez to jednak **danymi osobowymi**. Kto niczego
  nie ustawia, dostaje teraz procedurę wyjmującą dane z RODO: wszystkie
  trafienia jednego rodzaju nazywają się tak samo (`[NAZWISKO]`).
  Numeracja pozostaje wyborem, stoi bez zmian w tym samym oknie;
  istniejące ustawienia pozostają, jakie są. W wierszu poleceń
  `--pseudonymisieren” (także `--mit-nummerierung`) przywraca.

- **Zanonimizowanych zastępników nie da się już przywracać pojedynczo.**
  Kto anonimizuje, dostaje dla każdej osoby ten sam zastępnik – i przez
  to nie ma już pojedynczego miejsca należącego do konkretnego nazwiska.
  Okno poprawek mimo to oferowało „Cofnij zastąpienie”: kliknięcie
  wstawiłoby *jedną* z wartości we *wszystkich* miejscach. Wiersze są
  teraz przygaszone jak przy zaciemnionych danych, kliknięcie mówi
  powód, a ręcznie dociągnięte znalezisko nie dostaje już numeru
  nigdzie nie występującego w reszcie dokumentu.

  Z tego samego powodu po przebiegu anonimizującym nie ma już
  „Przetłumacz odpowiedź z powrotem” – wcześniej wstawiłoby obce
  nazwisko w miejsce każdej osoby. Kto potrzebuje tej pętli, wybiera
  „Pseudonimizuj”; aplikacja mówi to teraz też tak, zamiast odsyłać do
  wygasłego przyporządkowania.

  W wierszu poleceń `--zuordnung` przy anonimizacji przerywa się teraz,
  zamiast pisać plik niebędący tłumaczeniem powrotnym – w oknie znacznik
  był już od dawna zablokowany. Albo `--pseudonymisieren` do tego, albo
  pominąć `--zuordnung`; komunikat to mówi. Wynik przy tym w ogóle nie
  powstaje, żeby skrypt nie został z połowiczną pracą.

- **Kanał aktualizacji stoi teraz na nowo na „Stabilny”.** Bez własnego
  wyboru kanał kierował się dotychczas tym, z jakiej budowy pochodziła
  działająca wersja – kto raz wypróbował wersję testową, dostawał od
  tamtej pory trwale oferowane wersje testowe. Zmiana kanału jest
  decyzją i ma nią też pozostać; wartość domyślna to dlatego „Stabilny”.
  Ustawione kanały pozostają nienaruszone.

### Ulepszone

- **„Postępowanie skargowe” nie liczy się już jako nazwa
  miejscowości.** W nagłówku „Notatka do akt – postępowanie skargowe 12
  C 345/26” program zaciemniał postępowanie razem: model językowy uważał
  je za miejscowość, niezależnie od otoczenia. Objęte jest nie
  pojedyncze słowo, tylko **rdzeń** złożenia – „postępowanie” i „notatka”
  obejmują przez to też postępowanie biznesowe, księgowe i płatnicze
  czy notatkę telefoniczną. Z trzydziestu sprawdzonych pojęć
  administracyjnych wcześniej trzy wywoływały fałszywy alarm, teraz już
  żadne; znajdywane jest nadal wszystko, co stoi obok („Postępowanie
  skargowe: Bernd Meisinger” traci nazwisko, nie nagłówek).

- **Anonimizowanie znów prowadzi księgę – dla dopasowania i
  dziennika.** W trybie anonimizującym program nie zapamiętywał
  znalezionych wartości. Przez to milczały dwie rzeczy: dokumentowe
  dopasowanie spójności (nazwisko rodowe pojawiające się później samo,
  pozostawało) i lista zastąpień w dzienniku sprawdzeń. Dopóki
  anonimizowanie było rzadszym wyborem, ledwie było to zauważalne – jako
  wartość domyślna stałoby się przypadkiem zwykłym. W dokumencie nic się
  nie zmienia: zastępnik pozostaje bez numeru.

- **„Brak danej osobowej” nazywa się teraz „brak danej osobowej”.** W
  dialogu przywracania i w ostrzeżeniu o twarzach stała prawnicza
  *dana* – liczba pojedyncza od „danych”. Była czytana jako dzień
  kalendarzowy, tym bardziej że aplikacja w innym miejscu oferuje
  „Usuwaj też daty”. Nazywa się teraz wszędzie „dana”, tak jak w
  czterech powodach powyżej w tym samym oknie.

- **Wiersz pochodzenia stoi już tylko w oknie „O programie”.** „Made
  with ♥ in Austria” siedział na dole okna głównego w środku rzędu
  przycisków i czytał się tam jak kolejny przycisk. Pozostaje dalej w
  oknie „O programie” – tam, gdzie się go szuka.

- **Obszar odkładania ma teraz widoczną krawędź.** Jej przerywany
  brzeg był tak blady, że ledwie odróżniał się od okna – to było
  obojętne, dopóki obszar był tylko obszarem. Odkąd jest przyciskiem,
  który da się osiągnąć klawiszem Tab, ta linia jest jedyną rzeczą
  pokazującą go jako element obsługi; jest dlatego podniesiona do
  wartości wymaganej przez normę.

## 0.10.22-beta.1 – 15 sierpnia 2026

### Nowe

- **Gdy obserwacja schowka jest wyłączana, jest naprawdę wyłączona.**
  Strażnik trzyma ostatnie treści w pamięci roboczej, żeby dało się
  odłożyć oryginał – dotychczas nawet wtedy, gdy Państwo wyłączyli
  obserwację. Teraz historia jest zapominana przy wyłączeniu. Kosztuje
  to przywracania po wyłączeniu, i dokładnie tak to jest pomyślane:
  wyłączone znaczy wyłączone.
- **Dziennik błędów nie zawiera już ścieżek plików.** Leżał tylko na
  Państwa komputerze i nigdy nie był wysyłany sam z siebie – ale
  prowadził ścieżki jawnym tekstem, a nazwa pliku często zdradza więcej
  niż treść. Z „…/Rozwod_Kowalski_Ugoda.docx” powstaje teraz przy zapisie
  `<plik>.docx`; rozszerzenie pozostaje, bo liczy się przy szukaniu
  błędu. To samo dotyczy adnotacji po awarii.
- **Lista zastąpień ostrzega teraz sama w sobie.** Jest jedynym plikiem,
  w którym Państwa dane oryginału stoją jawnym tekstem, i leży obok
  wyniku – kto przekazuje folder, przekazuje ją razem. Teraz ostrzeżenie
  stoi jako pierwszy wiersz **w** pliku, obszar wyjścia podaje pełną
  ścieżkę zamiast tylko nazwy pliku, a w wierszu poleceń plik jest w
  ogóle po raz pierwszy wspominany: dotychczas w ogóle się nie
  dowiadywano, że powstał.
- **Anonimizowanie lub pseudonimizowanie jest teraz nazwanym wyborem.**
  W tym miejscu stał dotychczas znacznik „Nazywaj te same nazwiska tak
  samo – SI wtedy jeszcze rozpoznaje, kto jest kim”. Opisywał korzyść i
  przemilczał skutek: ponumerowane zastępniki (`[NAZWISKO_1]`,
  `[NAZWISKO_2]`) to **pseudonimizacja**, a pseudonimizowane dane
  pozostają danymi osobowymi – kto wierzył, że w ten sposób
  zanonimizował, mylił się. Teraz oba tryby stoją obok siebie, każdy ze
  swoją ceną. Wartością domyślną pozostaje pseudonimizowanie, bo dokument
  czytany potem lub przetwarzany przez SI potrzebuje swoich odniesień.
  Przy anonimizowaniu lista zastąpień jest zablokowana: uczyniłaby
  wynik znów odwracalnym. Podręcznik i FAQ wyjaśniają różnicę we
  wszystkich 18 językach; w wierszu poleceń przełącznik nazywa się teraz
  też `--anonymisieren`.
- **Wiersz nad obszarem odkładania mówi teraz, co naprawdę jest
  prawdą.** Obiecywał „100% lokalne przetwarzanie – bez chmury i konta,
  zgodne z RODO”. Dla Państwa dokumentów to prawda, dla programu nie w
  tej ogólności: szuka aktualizacji, na życzenie zgłasza błędy,
  doładowuje modele i zgłasza kupione stanowiska pracy. Teraz stoi tam
  węższe i solidne stwierdzenie: Państwa dokumenty nie opuszczają
  komputera.
- **Przy wyniku stoi teraz zawsze, że trzeba go sprawdzić.** Dotychczas
  Maskuro po gładkim przebiegu zgłaszał „Usunięto 12 danych” na zielono i
  poza tym nic – to czyta się jak zapewnienie, że znaleziono wszystko.
  Wskazówki pojawiały się tylko wtedy, gdy konkretnie czegoś nie dało
  się sprawdzić (obrazy, nieznane załączniki). Teraz pod każdym wynikiem
  stoi w sposób niemożliwy do przeoczenia, że nie w każdym przypadku
  wszystkie dane osobowe są rozpoznawane, że sprawdzenie leży po
  stronie użytkownika i że brakujące trzeba uzupełnić ręcznie – w oknie,
  w obszarze wyjścia i w wierszu poleceń. Żadnego okna komunikatu do
  odklikania: zdanie stoi tam trwale. Krótka instrukcja mówi to teraz
  tymi samymi słowami.
- **Po aktualizacji przy starcie stoi, co się zmieniło.** Dotychczas
  aktualizacja przebiegała po cichu i nie dawała się odróżnić od
  ponownego uruchomienia. Teraz pojawia się jednorazowo „Co nowego” – a
  kto pominął jedną wersję, widzi też to, co było między nimi. Nie przy
  zupełnie pierwszym uruchomieniu: tam nadal wprowadza krótka
  instrukcja.
- **Chiński i japoński znajdują teraz nazwiska.** Dotychczas nie
  znajdowały **żadnych** – nie mało, żadnych. Obu modelom językowym
  brakowało segmentacji słów, bez której zdanie bez spacji liczy się
  jako jedno jedyne słowo; program po cichu przechodził na model
  wielojęzyczny zastępczy. Oba języki rozpoznają teraz osoby i
  miejscowości jak pozostałe. Słownik japoński jest przy tym wczytywany
  razem z językiem i nie leży w programie – sam w sobie ważyłby dobre
  200 MB, które inaczej niósłby każdy.
- **Rumunia jest wybieralna jako kraj.** Dotychczas w ogóle brakowało.
  Dzięki temu rozpoznawane są rumuńskie adresy („Strada Victoriei 30”),
  kody pocztowe z miejscowością („010061 București”) i Cod Numeric
  Personal – ten ostatni tylko z pasującą cyfrą kontrolną, żeby nie
  zaznaczać każdej trzynastocyfrowej liczby na fakturze. Do tej pory w
  rumuńskich dokumentach kod pocztowy pozostawał czytelny obok
  zaciemnionej nazwy miejscowości.
- **„Rasteryzuj stronę” w edytorze.** Jeśli tekstu z PDF nie da się
  usunąć – zdarza się to przy plikach obcych generatorów – strona jest
  teraz na życzenie zastępowana swoim odwzorowaniem: tekst jest przez to
  bezpowrotnie usunięty, strona pozostaje czytelna i przeszukiwalna.
  Ostrzeżenie zgłaszające ten przypadek oferuje ten krok od razu jako
  przycisk; przez „Narzędzia → Rasteryzuj stronę” działa też samodzielnie.
  Cofnij przywraca stronę.
- **Interfejs jest teraz dostępny też po chorwacku, grecku, litewsku,
  słoweńsku, japońsku i koreańsku.** Jest ich przez to osiemnaście
  języków. Podręcznik, FAQ i teksty prawne są w pełni dostępne we
  wszystkich sześciu. Etykiety w oczyszczonym dokumencie podążają przy
  tym za interfejsem – z `[NAME_1]` powstaje `[IME_1]`, `[ΟΝΟΜΑ_1]`,
  `[VARDAS_1]` lub `[氏名_1]`. **Przy grecku, japońsku i koreańsku
  etykiety stoją po łacinie** – `[ONOMA_1]`, `[SHIMEI_1]`, `[IREUM_1]`.
  Interfejs pozostaje w swoim własnym piśmie; tylko to, co jest
  wpisywane do dokumentu, jest łacińskie. Powodem jest zestaw znaków
  PDF: tam greckie i japońskie etykiety wcześniej przychodziły jako
  `[??_1]`, i przez to nie dało się już odróżnić nazwiska od
  miejscowości.
- **Dochodzi dziewięć krajów, a siedem istniejących staje się
  kompletnych.** Nowo rozpoznawane są numery dowodu, podatkowe i
  ubezpieczenia społecznego wraz z adresami dla **Chorwacji, Słowenii,
  Grecji, Litwy, Macedonii Północnej, Rosji, Ukrainy, Chin i Japonii**.
  Przy istniejących krajach zamknięto luki, które ważyły ciężej: dla
  **Holandii** i **Portugalii** w ogóle nie było dotychczas numeru
  osobowego – holenderski BSN i portugalski NIF nie były rozpoznawane,
  mimo że stoją na praktycznie każdym piśmie tych krajów. Polska
  dostaje numer podatkowy NIP, Dania, Norwegia i Finlandia swoje adresy,
  Kanada swój kod pocztowy. Jest ich dzięki temu **35 krajów**.

### Usunięte

- **Dla Linuksa na razie nie ma już pakietu.** Kod źródłowy tam działa,
  ale brakuje pod Linuksem trzech rzeczy, które ta instrukcja obiecuje:
  automatyczny start, globalne skróty klawiszowe i – zależnie od
  środowiska pracy – ikona na pasku. Wydanie pakietu potrafiącego mniej
  niż opisano byłoby złą drogą. Windows i macOS są nienaruszone.

### Ulepszone

- **Sygnatury akt są teraz znajdywane we wszystkich językach.**
  „Aktenzeichen 12/2026-AB” było usuwane, „File reference 12/2026-AB”
  czy „Sygnatura 12/2026-AB” pozostawały: słowa pola, po których Maskuro
  rozpoznaje taki numer, istniały tylko po niemiecku. Teraz zna
  odpowiedniki w dwunastu językach – i jak dotychczas zastępowany jest
  tylko numer, etykieta przed nim pozostaje, żeby w wyniku było widać,
  co tam usunięto.
- **Maskuro zajmuje w bezczynności około pół gigabajta mniej.** Przy
  starcie był dotychczas wczytywany też model dodatkowy dokładniejszego
  rozpoznawania, żeby pierwsze oczyszczanie na niego nie czekało.
  Zmierzono, że kosztowało to 648 MB pamięci roboczej i oszczędzało 1,9
  sekundy – i kosztowało to też wtedy, gdy Państwo tylko otworzyli okno
  i znów je zamknęli. Model jest teraz wczytywany przy pierwszej
  potrzebie; wiersz stanu o tym informuje. Model językowy jest nadal
  wczytywany przy starcie – tego od razu potrzebuje obserwacja schowka.
- **Obszar odkładania da się teraz obsługiwać też bez myszy.**
  „Przeciągnij pliki tutaj” był obszarem reagującym na kliknięcia – z
  klawiaturą się tam nie docierało, a czytnik ekranu odczytywał go jako
  ramkę z tekstem w środku, nie jako to, czym jest. Jest teraz
  przyciskiem: klawisz Tab go osiąga, spacja i Enter otwierają wybór
  pliku, a kto go osiągnął, widzi to po krawędzi. Przez menu „Plik →
  Wybierz pliki” dało się to już wcześniej, ale trzeba było o tym
  wiedzieć.
- **Nazwa oczyszczonego pliku jest teraz też odczytywana na głos.** Na
  liście plików stoi jako drugi, mniejszy wiersz pod oryginałem – ale
  był tam tylko narysowany, a czytnik ekranu nazywał wyłącznie
  oryginał. Akurat ten wiersz jest zbudowany przeciwko pomyłce, że
  przebieg był bezskuteczny, bo w folderze leży nietknięty oryginał.
  Wiersz brzmi teraz odczytany „faktura.pdf, wynik:
  faktura_bereinigt.pdf”.
- **Elementy obsługi bez etykiety mówią teraz, do czego służą.** Przyciski
  symboliczne na liście plików, przyciski rysunkowe w oknie poprawek i
  wszystkie pola wyboru i wpisu były dla czytników ekranu bezimienne –
  zapowiadane jako „przycisk” i „pole kombi”, bez tego czego. Przyciski
  przy wierszu nazywają przy tym plik: na liście z dwudziestoma wpisami
  słyszało się inaczej dwadzieścia razy to samo zdanie.
- **Kto obsługuje klawiaturą, znów widzi, gdzie stoi.** Przycisk
  „Oczyść” i przyciski symboliczne na liście plików są kolorowe, i przez
  to zniknęła ramka, którą system inaczej rysuje wokół osiągniętego
  elementu obsługi – przy przechodzeniu Tab wzrok trafiał w próżnię. Oba
  mają teraz własną ramkę, gdy tylko przychodzi ich kolej. Przyciski nie
  zmieniają przy tym rozmiaru.
- **Siedem kolorów pisma było zbyt bladych, w obu wyglądach.**
  Zmierzone wg zwyczajowej normy (WCAG 2.1) blade wiersze wskazówek,
  teksty poboczne na strefie odkładania, punkty instrukcji i w ciemnym
  obrazie dodatkowo niebieski i czerwony leżały poniżej granicy 4,5:1 –
  czytelne przy dobrym świetle i dobrym wzroku, inaczej nie. Wszystkie
  są podniesione; stopniowanie pozostaje, teksty czytają się nadal jako
  poboczne. Trzy dalsze – kolory, w których zgłaszane są ostrzeżenia i
  sukces – trzymały granicę ledwie i są dociągnięte razem: kto ich nie
  czyta, nie czyta informacji, czy coś poszło źle. Widocznie zmienił się
  przy tym tylko przycisk „Oczyść” w ciemnym obrazie: nosi teraz ciemne
  zamiast białego pisma, jak przyciski akcentowe Windows 11 również.
- **Każdy wiersz listy plików ma teraz swój własny krzyżyk.**
  Dotychczas trzeba było najpierw zaznaczyć wiersz, a potem kliknąć
  „Usuń” – dwa kroki dla drobnostki. Krzyżyk stoi po prawej w wierszu i
  potrzebuje jednego. Przycisk „Usuń” pod spodem przez to odpadł; kto
  chce pozbyć się kilku wierszy naraz, zaznacza je i bierze wpis w menu
  kontekstowym, który też mówi, ile ich jest. „Usuń wszystko” pozostaje.
  Z listy zabierany jest zawsze tylko wiersz – nigdy plik na dysku.
- **Przed sprawdzeniem SI stoi teraz, czy ten komputer się do tego
  nadaje.** Dotychczas w oknie stało tylko, jak duży jest model. Kto
  włączał go na słabym komputerze, zauważał dopiero przy pierwszym
  dokumencie, że trwa to bardzo długo – po pobraniu 5,4 GB. Teraz okno
  podaje **wcześniej** pamięć roboczą i wolne miejsce oraz mówi, co to
  oznacza; **potem** mierzona jest prędkość i podawana w wielkości, o
  którą chodzi: „Dziesięciostronicowy dokument trwa na tym komputerze
  około 12 minut.” Jeśli jest za wolno, program odradza i oferuje
  ponowne wyłączenie poziomu – niczego nie zabrania.
- **Pomiar prędkości działa teraz na każdym komputerze.** Dotychczas
  przychodził tylko wtedy, gdy dodatkowo skonfigurowano przyspieszenie
  grafiki – istniejące tylko pod Windows. Na wszystkich innych
  komputerach program szacował więc czas trwania na podstawie obcego
  komputera, i akurat tam, gdzie jest wolno, szacunek się mijał.
- **Tureckie adresy są znajdywane też na skanie.** Na zeskanowanym
  nagłówku firmowym „34710 İstanbul” pozostawało czytelne, podczas gdy
  ta sama dana w tekście obok znikała: rozpoznawanie tekstu czyta
  tureckie İ bez jego kropki, a wzorzec oczekiwał wielkiej litery. To
  samo dotyczyło „Bağdat Caddesi”.
- **Hiszpańskie adresy bez własnej nazwy ulicy są znajdywane.** „Gran
  Vía 5” pozostawało, bo wzorzec za typem ulicy oczekiwał jeszcze słowa
  nazwy – przy „Calle Mayor” jedno jest, przy „Gran Vía” typ sam już
  jest nazwą. To samo dotyczy teraz „La Rambla” i „Castellana”.
- **W oknie „O tym programie” stoi teraz wskazówka o
  przejrzystości** dotycząca tego, że aplikacja została stworzona ze
  wsparciem sztucznej inteligencji. Dotyczy powstania programu, nie
  sposobu jego działania: oczyszczanie odbywa się nadal wyłącznie na
  własnym komputerze.
- **„Zarządzaj językami” pokazuje teraz najpierw użyteczne języki.** Dla
  połowy z 48 języków nie ma własnego modelu językowego; tam
  wielojęzyczny model zastępczy rozpoznaje nazwiska tylko słabo, w
  niektórych pismach wcale. Obok siebie na liście wszystkie wyglądały
  równorzędnie. Wartość domyślna pokazuje dlatego już tylko języki z
  własnym modelem – przez „Pokazane” pozostałe da się w każdej chwili
  włączyć, ze zdaniem o tym, co potrafią, a czego nie. Nic nie odpada, a
  kto skonfigurował ograniczony język, zachowuje go.
- **Pytanie o brakujący język nazywa teraz wyjście.** Gdy rozpoznawany
  jest język, dla którego jeszcze nic nie skonfigurowano, program
  oferował dotychczas tylko „Wczytaj” lub „Kontynuuj bez”. Rozpoznawanie
  może się jednak mylić – przy krótkich formularzach i listach z
  niewielką ilością tekstu głównego decydują nieliczne słowa. W oknie
  stoi teraz dlatego, że można przerwać i wybrać właściwy język ręcznie,
  zamiast używać „Rozpoznaj automatycznie”. Oszczędza to w razie
  wątpliwości pobranie kilkuset megabajtów dla języka, który wcale nie
  jest potrzebny.
- **Etykiety zastępników mówią teraz w języku interfejsu.**
  „[NAME_1]”, „[ADRESSE_2]” i podobne stały dotychczas zawsze po
  niemiecku, bez względu na to, jaki język był ustawiony lub w jakim
  języku napisany był dokument. Teraz podążają za językiem interfejsu –
  po angielsku więc „[NAME_1]”, „[ADDRESS_2]”. Nie za językiem
  dokumentu: ten jest przy „rozpoznaj automatycznie” zgadywany i czasem
  błędny; język interfejsu nigdy nim nie jest.
- **Mniej dopytywań przy poprawianiu.** Dokąd wynik jest zapisywany,
  stoi teraz trwale na dole na pasku („→ umowa_bereinigt.pdf”, w
  podpowiedzi folder) – kliknięcie w to wybiera inne miejsce, bez
  natychmiastowego zapisu. Pytanie zwrotne przy pierwszym zapisie przez
  to odpada. Pytanie „już edytowane – zacząć od nowa?” da się
  zapamiętać na sesję, a dwa okna wskazówek dające tylko informację
  stoją teraz w wierszu stanu. Pozostają pytania zapobiegające szkodzie
  nieodwracalnej: niezapisana praca przy zamykaniu i ostrzeżenie o
  nieusuniętym tekście.
- **Wynik mówi teraz, gdzie sam skan nie był czytelny.** Na
  zeskanowanym dokumencie rozpoznawanie tekstu urządzenia nie czyta
  wszystkiego poprawnie – z „Solarstraße 9” powstaje wtedy np.
  „Solaret^aß« B”. Tego, co tak błędnie odczytano, żadne sprawdzenie już
  nie znajdzie: dla każdego wzorca wyszukiwania wygląda to jak sałatka
  literowa. Program nic na to nie może poradzić, ale nazywa teraz takie
  miejsca z numerem strony – zwykle tkwią tam pieczątki, nagłówki
  firmowe lub odręczne dopiski. To wskazówka, nie ostrzeżenie: przy
  dokumencie składanym nie pojawia się.
- **Lista plików pokazuje teraz, jak nazywa się wynik.** Pod nazwą pliku
  po przebiegu stoi nazwa oczyszczonego pliku („→ umowa_bereinigt.pdf”).
  Dotychczas stała tylko w dzienniku za „Szczegóły”, a kto sprawdzał w
  folderze, znajdował nietknięty oryginał. Nazwa źródła pozostaje – w
  przeciwnym razie nie byłoby już widać, z którego pliku pochodzi wynik.
- **Przyciski w gotowym wierszu są większe i wyraźniejsze.** Zobacz,
  Popraw i „Pokaż w folderze” były płaskimi symbolami bez powierzchni i
  ginęły na liście – a przecież po przebiegu są jedynym, co się jeszcze
  klika.

### Naprawione

- **W obcojęzycznym interfejsie własne reguły zaciemniania,
  maskowania i haszowania były po cichu pomijane.** Kto ustalił, że
  nazwiska mają być zaciemniane zamiast zastępowane, dostawał je mimo
  to zastąpione – gdy tylko program był obsługiwany nie po niemiecku
  lub angielsku. Ustawienie stało tam, tylko nie działało, a w wyniku
  różnicy nie było widać. Dotyczyło to dziewięciu z dwunastu języków
  interfejsu.
- **Ustawienie „Język etykiet” nie działało poza niemieckim i
  angielskim.** „Niemiecki” i „Angielski” dały się wybrać, ale w
  dokumencie stał nadal język interfejsu. Teraz działają wszystkie trzy
  możliwości; wartość domyślna „jak interfejs” dostarcza bez zmian to
  samo co dotychczas.
- **W krótkich fragmentach tekstu nazwiska pozostawały – np. w
  skopiowanym cytacie maila.** Kto oczyszczał fragment przez schowek,
  dostawał tam często zaciemniony tylko adres e-mail, ale nie nazwisko
  pod nim. Decydowała sama liczba wierszy: od sześciu wierszy program
  rozpoznawał fragment jako zestawienie i znajdywał nazwiska, poniżej
  nie – skopiowany cytat maila ma pięć. Dowolny dodatkowy wiersz, np.
  temat, przechylał wynik. Teraz wystarczą cztery wiersze, a w pomiarze
  znikają wszystkie sprawdzone nazwiska zamiast jednej trzeciej. Na
  dłuższe dokumenty i tekst główny to nie wpływa.
- **Przyspieszenie grafiki sprawdzenia SI było dotychczas znów
  wyłączane, gdy tylko się je skonfigurowało.** Po konfiguracji program
  mierzy, czy grafika na tym komputerze jest naprawdę szybsza niż
  procesor – ten pomiar jednak zawsze się nie powodził, bez mówienia
  tego, a wynik „oba tak samo szybkie” decydował na korzyść procesora.
  Kto wczytał 65 MB, dostawał potem mniej niż wcześniej. Pomiar teraz
  działa; jeśli zawiedzie, niczego już nie zmienia.
- **Szacunek czasu liczył na każdym komputerze z obcą prędkością.**
  Opiera się na tym samym pomiarze; dopóki on nie działał, obowiązywała
  wartość komputera deweloperskiego. „Około dwie minuty” mogło przez to
  na wolnym komputerze oznaczać pół godziny.
- **Poziom SI pracuje z nowym, wyraźnie lepszym modelem językowym**
  (Qwen3.5-9B zamiast Qwen3-4B) i nie jest już ograniczony do niemieckiego
  i angielskiego, tylko pracuje w dwunastu językach. Zmierzone na
  korpusie testowym: tyle samo znalezionych danych co bez poziomu, ale
  mniej niż połowa zbędnych zaciemnień (75 → 31). Model jest większy
  (5,4 zamiast 2,4 GB) i potrzebuje mniej więcej dwukrotnego czasu
  obliczeń; przy włączaniu jest wczytywany jednorazowo, stary przy tym
  usuwany.
- **Adresy po francusku, włosku, hiszpańsku, portugalsku, polsku,
  turecku i szwedzku są teraz w pełni usuwane.** Dotychczas znikała tam
  tylko nazwa ulicy i miejscowości – numer domu i kod pocztowy
  pozostawały czytelne („[MIEJSCE_1] 28, 28013 [MIEJSCE_2]”). Dla tych
  języków nie było własnych wzorców adresowych; są teraz uzupełnione.
- **Grecki i koreański w ogóle nie znajdowały nazwisk.** Przy grecku
  leżało to w modelu zastępczym – z własnym modelem, który da się teraz
  wczytać, nazwiska i miejscowości są rozpoznawane czysto. Przy
  koreańskim leżało to w programie: zakładał, że nazwisko zaczyna się
  wielką literą, a hangul nie zna wielkich liter. Dotyczyło to przede
  wszystkim krótkich jednostek – komórek tabeli, pól formularza, wpisów
  listy.
- **Model językowy, którego nie dało się wczytać, przerywał
  oczyszczanie.** Zamiast komunikatu błędu wskakuje teraz model
  wielojęzyczny, a wynik wskazuje, że pracowano ze słabszym
  rozpoznawaniem. Dotyczy obecnie chińskiego i japońskiego, których
  modele wymagają segmentacji słów, jeszcze nie dołączonej do programu.
- **Język z własnym modelem liczył się jako zainstalowany, gdy tylko
  wczytany był jakikolwiek inny.** Kto konfigurował np. turecki, dostawał
  przez to model wielojęzyczny zastępczy – a chiński, japoński,
  koreański lub grecki stały potem na liście z zaznaczonym znacznikiem i
  „0 MB”, mimo że brakowało ich własnego modelu. Przez to nigdy nie dały
  się doładować i pracowały trwale ze słabszym zastępnikiem. Teraz lista
  pokazuje rzeczywisty stan wraz z rozmiarem wczytywania.
- **Zawiedziony poziom rozpoznawania milczał.** Jeśli „Rozszerzone
  rozpoznawanie” lub „Maksymalne rozpoznawanie (SI)” było włączone, ale
  modelu nie dało się uruchomić, program pracował dalej bez tego
  poziomu – bez słowa na ten temat. Wynik wyglądał jak każdy inny, a
  przełącznik stał nadal na „włączone”: uważano więc wynik poziomu
  podstawowego za najlepszy, jaki dało się osiągnąć. Wynik mówi to teraz
  i podaje oba: co nie zostało sprawdzone i jak ponownie wczytać model.
  Przypadek nie jest rzadki: na niektórych komputerach poziom SI zawodzi
  przy wczytywaniu, gdy brakuje przyspieszenia grafiki.
- **Błąd przy wczytywaniu modelu dodatkowego przerywał całe
  oczyszczanie.** Przy „Rozszerzonym rozpoznawaniu” zabezpieczona była
  tylko ocena modelu, nie jego wczytanie – a właśnie tam coś idzie źle,
  gdy plik jest uszkodzony lub nie pasuje do komputera. Zamiast
  komunikatu błędu jest teraz wynik poziomu podstawowego wraz ze
  wskazówką.
- **Języka nie dało się już usunąć – a przez to też ponownie
  wczytać.** Kto w „Zarządzaj językami” zdejmował znacznik i
  zatwierdzał zmianę, czytał „Niemiecki usunięty”, ale widział znacznik
  od razu z powrotem ustawiony. Przyczyną było przejmowanie z folderu
  programu: przy instalacji dla wszystkich użytkowników modele
  językowe leżą w folderze programu chronione przed zapisem, a program
  pobiera stamtąd brakujące zamiast wczytywać na nowo setki megabajtów.
  To przejmowanie działało przy każdym dostępie – i kopiowało właśnie
  usunięty język w tym samym oddechu z powrotem. Odbywa się teraz
  jednorazowo; doładowane modele językowe pozostają przy tym zachowane.
  Ponadto program po usunięciu sprawdza: to, czego nie dało się usunąć,
  jest teraz zgłaszane jako niepowodzenie zamiast jako „usunięte”.
- **Przy instalacji dla wszystkich użytkowników nie dało się odłożyć
  doładowanego.** Kto instaluje program dla wszystkich użytkowników, ma
  go w „Program Files”, a tam bez uprawnień administratora nic się nie
  zapisuje. Dla modeli językowych było do tego od dawna przewidziane
  miejsce zastępcze, dla reszty nie:
  - **Komponent podglądu strony** był po pobraniu 290 MB rozpakowywany
    do folderu programu i tam zawodził – bez podania powodu. Leży teraz
    przy modelach językowych, gdzie zgodnie z zamierzeniem zawsze
    powinien leżeć.
  - **Przyspieszenie grafiki** nie może uciec: wymienia biblioteki w
    samym programie. Zamiast najpierw wczytywać, a potem bezsłownie
    zawodzić, program mówi teraz z góry, że tu się nie da i co to
    znaczy – maksymalne rozpoznawanie działa dalej, tylko przez
    procesor.
  - Dołączonego **języka rozpoznawania tekstu** nie dało się usunąć:
    był z folderu programu od razu przywracany z powrotem. Ta sama
    przyczyna co przy modelach językowych, to samo rozwiązanie.
  - Przy usuwaniu języka mogły być usuwane **dane językowe obcej
    instalacji Tesseract**. Dotykany jest teraz tylko własny folder.
  - Miejsce zastępcze obowiązywało dotychczas tylko pod Windows.
    Archiwum Linux do `/opt` miało tę samą biedę bez tego samego
    wyjścia.
- **Przy poprawianiu znikał cały wiersz, mimo że oramkowane było tylko
  jedno słowo.** Kto w już oczyszczonym pliku zaciemniał zastępnik,
  tracił wiersz, w którym stał: z „Szanowna Pani Doktor [NAZWISKO_1]”
  nic nie zostawało – a komunikat mówił przy tym „usunięto jedno słowo z
  dokumentu”. Dotyczyło to każdego pliku, który już raz przeszedł przez
  program, więc akurat przypadku, dla którego istnieje poprawianie.
  Pozostały tekst pozostaje teraz nienaruszony, na niezmienionym
  miejscu.
- **„EMPLOYEES” nad listą nazwisk było samo zaciemniane.** Ten sam
  przypadek co „MITARBEITER” w 0.10.19, tylko po angielsku – tam
  pozostał. W wielkich literach modelowi językowemu brakuje cechy
  rozróżniającej, a nagłówek stoi nad samymi prawdziwymi nazwiskami.
  Nazwiska pod spodem są nadal znajdywane. Nie dodano „staff”: to jest
  uznane nazwisko, a wpis zabierałby każdego „John Staff” – ta sama
  ocena co swego czasu przy „Arbeiter”.
- **Forma prawna była zastępowana po raz drugi.** Na zeskanowanym
  nagłówku firmowym model językowy czytał „GmbH”, adres i kod pocztowy
  jako **jedną** miejscowość. Adres i kod pocztowy wycinały potem swoje
  kawałki, a formą prawna pozostawała jako osobne trafienie: w wyniku
  stało „[MIEJSCE_1] [MIEJSCE_2]”, gdzie chodziło o „[MIEJSCE_1] GmbH”.
  Nazwa firmy jest nadal zastępowana – tylko nagi dodatek pozostaje
  teraz, a wynik czyta się jak nagłówek firmowy zamiast jak ćwiczenie z
  luką.
- **Przycięte trafienie nie było sprawdzane ponownie.** Przyczyna
  przypadku powyżej, a sięga dalej: filtry przeciw zgadniętym trafieniom
  działały na tym, co rozpoznawacze **zgłaszają** – nie na tym, co
  pozostaje po rozwiązaniu nakładania. Jeśli długie trafienie jest
  przycinane przez silniejszy rozpoznawacz, fragment jest innym tekstem
  niż oceniony, i nikt nie przyjrzał się mu jeszcze raz. Teraz tak.
- **„Używają Państwo najnowszej wersji” – mimo że w ogóle nie dało się
  sprawdzić.** Kto ustawił jako kanał aktualizacji „Zapoznawcza (beta)”
  lub „Stabilna – zalecana”, dostawał tę informację, mimo że na tych
  kanałach dotychczas nic w ogóle się nie ukazało. Program mówi teraz
  dokładnie to – i proponuje wybór innego kanału w ustawieniach.
- **Zamknięcie okna podczas wczytywania powodowało awarię wątku.** Kto
  uruchamiał Maskuro i od razu zamykał okno, podczas gdy modele
  językowe jeszcze się wczytywały, dostawał w dzienniku raport błędu:
  proces wczytywania zgłaszał się do okna, którego już nie było.
  Widocznych skutków to nie miało, ale w dzienniku stała awaria, gdzie
  ktoś był tylko szybszy niż program.
- **Wynik jest teraz oglądany, nie tylko odczytywany.** Dotychczas
  strona liczyła się za czystą, gdy wartość nie stała już w tekście. Na
  skanie to nie jest dowód – tam widoczny tekst jest obrazem. Na koniec
  sprawdzane jest więc, czy powierzchnia w wyniku jest naprawdę
  zaciemniona; jeśli stoi tam nadal jasny papier, raport mówi to
  wyraźnie, zamiast zgłaszać „zastąpione”.
- **Zastąpiona dana pozostawała na obrazie.** Jeśli wartość stała na
  obrazie – zeskanowany nagłówek firmowy, pieczątka, cała zeskanowana
  strona – była wprawdzie usuwana z tekstu dokumentu, ale nadal
  **widoczna**: to, co czyta człowiek, są tam piksele. Raport mimo to
  zgłaszał „zastąpione”. Teraz powierzchnia w obrazie jest zaciemniana,
  bez względu na to, jaka strategia jest ustawiona, a zastępnik stoi
  jasno na tym tle – brzydko, ale uczciwie, a przyporządkowanie
  pozostaje zachowane. Jeśli formatu obrazu nie da się obrobić, wynik
  mówi to teraz wyraźnie, zamiast wyglądać czysto.
- **Na skanie zastępnika w ogóle brakowało.** Warstwa tekstu
  zeskanowanej strony jest rysowana niewidocznie, a zastępnik wstawiony
  w nią odziedziczył to: ustawiony, ale niewidoczny. W miejscu
  znalezienia nic potem nie stało.
- **Rozpoznawanie tekstu, które w ogóle nie mogło działać, uchodziło za
  zaliczone.** Jeśli brakowało pliku językowego lub silnik
  rozpoznawania się przerywał, raport zgłaszał „obraz(y) … zostały
  sprawdzone przez rozpoznawanie tekstu (0 miejsc znalezienia)” – więc
  sprawdzenie, które nigdy się nie odbyło. Przy skanie to jedyne
  sprawdzenie w ogóle: umowa z czytelnym adresem na obrazie strony
  uchodziła przez to za gotową. Teraz raport mówi, że nic nie zostało
  sprawdzone, i dlaczego.
- **Plik językowy był szukany w niewłaściwym folderze.** Jeśli we
  własnym katalogu językowym leżały inne języki niż język dokumentu,
  silnikowi rozpoznawania podsuwano akurat ten katalog i się nie
  powodziło – mimo że pasujący język leżał obok. Szukany jest teraz
  **język**, nie folder.
- **Ostrzeżenie o nieusuniętym tekście radziło coś, czego nie ma.**
  Odsyłało do „Zaciemnij jako PDF” – ale to tworzy widok PDF z plików
  *biurowych* i przy PDF w ogóle nie jest dostępne. Kto chciał postąpić
  według ostrzeżenia, szukał na próżno. Teraz stoi tam przycisk, który
  załatwia sprawę.
- **W edytorze pasy i zastępniki lądowały obok zaznaczonego miejsca.**
  Dotyczyło to każdego PDF-u, w którym wiersz kończy się na łączniku, a
  słowo w następnym idzie dalej – przy skanach jest to szczególnie
  zauważalne, bo teksty umów są konsekwentnie dzielone. Obie połówki
  wiersza liczyły się jako *jedno* słowo rozciągające się w poprzek
  łamu, a każda ramka w jego pobliżu przejmowała ten zasięg. Samo
  rozpoznawanie się przez to nie zmienia: korpus pomiarowy dostarcza
  ten sam wynik co wcześniej.
- **Edytor ostrzegał, że tekst „nadal stoi w dokumencie”, mimo że był
  usunięty.** Jeśli to samo słowo pojawiało się na stronie kilkakrotnie
  – w umowach to reguła – samosprawdzenie po każdej ingerencji zgłaszało
  niepowodzenie. Liczy teraz wystąpienia, zamiast tylko sprawdzać, czy
  słowo gdziekolwiek jeszcze stoi. Przy prawdziwym niepowodzeniu
  ostrzega bez zmian.
- **Plik wynikowy nazywał się w każdym języku „_bereinigt”.** Chodziło
  zawsze o to, żeby dodatek nazwy podążał za językiem interfejsu – po
  angielsku tak się działo („_cleaned”), w pozostałych szesnastu
  językach nie. Kto używał programu po fińsku, dostawał
  „asiakirja_bereinigt.pdf”. Teraz plik nazywa się
  „asiakirja_puhdistettu.pdf”, po japońsku „書類_除去済み.pdf” i tak dalej
  – każdorazowo słowem, którego ten sam interfejs używa w swoim
  komunikacie o zakończeniu. Kto ustawił własny dodatek, zachowuje go.
- **„Zarządzaj językami” nazywało się zawsze po niemiecku.** Na liście
  48 języków dokumentu stały niemieckie nazwy, bez względu na to, jaki
  interfejs był ustawiony: fiński użytkownik czytał „Chinesisch”. Teraz
  stoi tam nazwa w jego języku, a za nią nazwa własna – „Kiina (中文)”.
  Nazwa własna jest zamierzona: kto rozpoznaje język po jego własnej
  nazwie, znajduje go też wtedy, gdy fińskie słowo nic mu nie mówi.

## 0.10.19 – 12 sierpnia 2026

### Ulepszone

- **Wpis w menu kontekstowym mówi teraz w Państwa języku.** Dotychczas
  stał tam w każdym systemie niemiecki tekst – nawet na angielskim
  Windows. Teraz podąża za ustawionym językiem interfejsu, a kto zmienia
  język, dostaje wpis natychmiast przemianowany, bez ponownej instalacji.
  (Windows; pod macOS i Linux nazwa menu jest jednocześnie nazwą pliku –
  to nastąpi później.)
- **Edytor zapamiętuje, w którym widoku Państwo ostatnio pracowali.** Kto
  używa podglądu strony, dostaje go przy następnym dokumencie sam z
  siebie – bez włączania go za każdym razem. Kto nigdy go nie używał,
  niczego nie zauważa: jest przywracany tylko wtedy, gdy potrzebny do
  tego moduł jest już wczytany, nigdy nie jest przy tym nic doładowywane.

### Naprawione

- **„PRACOWNICY” nad listą nazwisk było samo zaciemniane.** W spisach
  pracowników i schematach organizacyjnych nagłówek znikał jako rzekome
  nazwisko – stoi tam nad samymi prawdziwymi nazwiskami, a wielkim
  literom brakuje dla modelu językowego cechy rozróżniającej. Nazwiska
  pod spodem są nadal znajdywane.
- **Dane ilościowe brano za adresy.** W fakturach, dokumentach dostawy i
  listach magazynowych znikały dane jak „3390 Protokół”, „1030 Kwota”
  czy „3390 Magazyn” jako rzekomy kod pocztowy z miejscowością –
  czterocyfrowa liczba wygląda jak austriacki kod pocztowy. Jeśli za
  liczbą stoi słowo, które aplikacja zna jako rzeczownik pospolity,
  dział, czynność lub etykietę pola, pozostaje teraz nienaruszone.
  Prawdziwe dane miejscowości są nienaruszone, także takie, które są
  jednocześnie takim słowem („4692 Miejsce”). Nie jest tym rozwiązany
  przypadek, gdy za liczbą stoi zupełnie zwykłe słowo („3390 Regał”) –
  do tego potrzebny jest spis kodów pocztowych.
- **Pomoc wymieniała punkt menu, którego nie ma.** Instrukcja, obraz i
  komunikat na końcu instalacji mówiły o „Oczyść dokument dla SI”; wpis
  w menu kontekstowym nazywa się jednak „Usuń dane osobowe”. Kto
  postępował według pomocy, szukał na próżno. Wszystkie trzy miejsca
  nazywają teraz punkt menu tak, jak się on naprawdę nazywa.
- **„Uruchamiaj z systemem” nie dawało się wyłączyć.** Kto podczas
  instalacji zaznaczył „Uruchom z Windows”, widział w ustawieniach mimo
  to pusty znacznik – a co gorsza: włączanie i wyłączanie w aplikacji
  pozostawało bez skutku, program dalej uruchamiał się z Windows.
  Przyczyną były dwa miejsca, w których Windows szuka programów
  startowych; aplikacja znała tylko jedno z nich. Teraz liczą się oba,
  przełącznik pokazuje prawdziwy stan i działa w obu kierunkach. Także
  uwzględnione: kto wyłącza wpis w Menedżerze zadań, widzi to teraz w
  aplikacji – a kto tam go z powrotem włącza, tym samym znosi
  wyłączenie.
- **Nagłówki nad listami nazwisk były zaciemniane.** „LISTA UCZESTNIKÓW
  ROZMOWY WARSZTATOWEJ” czy „PRZEGLĄD PRACOWNIKÓW DZIAŁU WEWNĘTRZNEGO”
  nad listą osób znikały jako rzekome nazwisko. W wielkich literach
  modelowi językowemu brakuje jego najlepszej cechy rozpoznawczej, a w
  niemieckim każdy rzeczownik jest pisany wielką literą – „Lista
  uczestników rozmowy warsztatowej” wygląda wtedy jak „Anna Huber”.
  Złożenia na `-liste`, `-dienst`, `-gespräch`, `-sitzung` i
  `-besprechung` pozostają teraz nienaruszone. Same wyrazy podstawowe
  nadal uchodzą za nazwiska: *Liste* i *Dienst* są uznanymi nazwiskami,
  *Teilnehmerliste* żadnym nie jest.
- **Dane ustawione pionowo dostawały nieczytelny zastępnik.** Sygnatury
  akt na marginesie strony, skróty osoby prowadzącej obok marginesu na
  oprawę, pionowe nagłówki tabel: takie dane były wprawdzie znajdywane i
  usuwane, ale zastępnik pojawiał się w poprzek tekstu, ściśnięty do
  jednego lub dwóch punktów, a czasem poza krawędzią papieru. Teraz
  podąża za tekstem – pionowo, w czytelnym rozmiarze i w tym samym
  kierunku, w jakim stały dane. To samo dotyczyło stron obróconych
  wtórnie (tekst pisany poziomo z wpisanym obrotem strony, jak dostarczają
  go niektóre programy wydające); także tam zastępnik stoi teraz tak, jak
  się patrzy na stronę. „Szanowna Pani Doktor Anneliese Berger” dawało
  tylko „Anneliese” jako nazwisko – „Berger” pozostawało w dokumencie. To
  samo dotyczyło każdego nazwiska z drugim imieniem („Pani Anna Maria
  Berger”). Przyczyną była reguła dla nazwiska za formą grzecznościową:
  miała dwa miejsca na słowa, a tytuł lub drugie imię zużywało pierwsze.
  Przy „Dr.” nigdy tego nie było widać – kropka łamie regułę, a model
  językowy chwytał całe nazwisko. Teraz tytuły są pomijane bez
  zajmowania miejsca, a nazwisko może składać się z trzech części. Rola
  **za** nazwiskiem nadal się nie liczy: „Pani Anna Huber Dyrektor
  Zarządzająca” zastępuje nazwisko, nie rolę.
