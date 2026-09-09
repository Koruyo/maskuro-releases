Co zmienia się z wydania na wydanie – opisane z perspektywy aplikacji, nie
jej wnętrza. Kto chce wiedzieć, *z czego* jest zbudowana, znajdzie to w
[LIZENZEN.md](LIZENZEN.md); tutaj stoi to, co zmienia się dla pracy z nią.

Numeracja stosuje zwykły sposób liczenia: **pierwsza** liczba zmienia się,
gdy coś nie działa już tak jak dotychczas, **druga** przy nowych
możliwościach, **trzecia** przy poprawkach błędów.

---

## 0.10.52-alpha.20260903 – 3 września 2026

- Partia obejmująca więcej niż cztery pliki nie zatrzymuje się już po
  udzieleniu odpowiedzi w kilku oknach podglądu. Kolejne dokumenty są nadal
  przygotowywane w tle; po odpowiedzi odpowiedni plik jest teraz zawsze
  przetwarzany do końca, a następne miejsce w kolejce zostaje zwolnione.
- Dopasowywanie krótkich oznaczeń firmowych w plikach PDF ogranicza się teraz
  do tekstu rozpoznanego na obrazach. Dzięki temu w zwykłym tekście strony
  długie, wielowierszowe trafienie modelu nie powoduje już dodatkowego
  zamaskowania takiego samego pojedynczego słowa w innym miejscu.

## 0.10.51-alpha.20260903 – 3 września 2026

- Lista zmian jest teraz wyświetlana w języku użytkownika – na
  maskuro.com/neuigkeiten oraz w programie w sekcji „Zmiany”, a także w oknie
  „Co nowego” po aktualizacji. Dotychczas we wszystkich osiemnastu wersjach
  językowych pod przetłumaczonym nagłówkiem znajdował się tekst po niemiecku.
  Jeśli tłumaczenia jeszcze brakuje, dana wersja pozostaje po niemiecku,
  zamiast znikać; lista wersji jest wszędzie taka sama.

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
