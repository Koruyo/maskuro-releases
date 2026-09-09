# Änderungen

Was sich von Fassung zu Fassung ändert – beschrieben aus Sicht der Anwendung,
nicht ihrer Innereien. Wer wissen will, *woraus* sie gebaut ist, findet das in
[LIZENZEN.md](LIZENZEN.md); hier steht, was sich für die Arbeit damit ändert.

Die Nummerierung folgt der üblichen Zählweise: Die **erste** Zahl ändert sich,
wenn etwas nicht mehr so funktioniert wie bisher, die **zweite** bei neuen
Fähigkeiten, die **dritte** bei Fehlerbehebungen.

---

## Unveröffentlicht

## 0.10.52-alpha.20260903 – 3. September 2026

- Ein Stapel aus mehr als vier Dateien bleibt nach mehreren beantworteten
  Vorschaufenstern nicht mehr stehen. Weitere Dokumente werden weiterhin im
  Hintergrund vorbereitet; nach einer Antwort wird die zugehörige Datei nun
  zuverlässig fertiggestellt und der nächste Platz im Stapel freigegeben.
- Der Abgleich kurzer Firmenzeichen in PDFs beschränkt sich nun auf erkannte
  Bildtexte. In gewöhnlichem Seitentext führt ein langer, mehrzeiliger
  Modelltreffer deshalb nicht mehr dazu, dass ein gleichlautendes Einzelwort
  an anderer Stelle zusätzlich geschwärzt wird.

## 0.10.51-alpha.20260903 – 3. September 2026

- Die Änderungsliste erscheint jetzt in der eigenen Sprache – auf
  maskuro.com/neuigkeiten und im Programm unter „Änderungen" sowie in „Was
  ist neu" nach einer Aktualisierung. Bisher stand dort in allen achtzehn
  Sprachfassungen deutscher Text unter einer übersetzten Überschrift. Wo eine
  Übersetzung noch fehlt, bleibt die betreffende Fassung auf Deutsch stehen,
  statt zu verschwinden; die Liste der Fassungen ist überall dieselbe.

## 0.10.50-alpha.20260903 – 3. September 2026

- Wiederkehrende Firmenzeichen in PDFs werden konsistent bereinigt, auch
  wenn die Texterkennung den Schriftzug auf einer Seite anders liest oder
  das runde Signet ganz auslässt. Eine ausdrückliche Abwahl in der Vorschau
  bleibt dabei verbindlich und kann von keinem späteren Nachzug aufgehoben
  werden.
- Währungslose Preise in gescannten Tabellen werden auch dann vollständig
  geschwärzt, wenn Tabellenkopf und Werte in verschiedenen überlappenden
  PDF-Bildern stecken. Mengen, Stunden, Gewichte und Prozente bleiben stehen;
  weit auseinanderliegende Zahlen werden nicht mehr versehentlich zu einem
  Betrag verbunden.
- Die Unterschriftensuche erfasst nun auch belegte schwache blaue Schriftzüge
  und schmale rote Signaturkürzel. Gepunktete Diagramme, Messkurven, Stempel,
  Logos und breite rote Bearbeitungsmarkierungen bleiben von diesem engen
  Nachzug ausgenommen.
- Schwärzungen in gedrehten, gespiegelten, gescherten oder beschnittenen
  PDF-Bildern treffen jetzt das wirkliche Bildpolygon. Technische Rollen in
  Leistungspositionen, Fahrzeug- und Reifensachwerte sowie technische
  „Kompensation“ werden zugleich enger gegen falsche Treffer abgegrenzt;
  ausdrücklich beschriftete Kontaktrollen und Rufnummern bleiben geschützt.
- Die Sichtprüfung vor dem Speichern einer PDF lässt das Fenster nicht mehr
  einfrieren: Bei großen Dokumenten mit vielen Fundstellen stand es bisher
  mehrere Sekunden ohne Rückmeldung; jetzt zeigt ein Hinweis, dass geprüft
  wird, und das Fenster zeichnet weiter.
- Das Zurückholen eines Werts aus einem Bild im Nachbessern-Editor liest
  jedes Originalbild nur noch einmal per Texterkennung; bisher lief sie bei
  jeder weiteren Rücknahme für dieselben Bilder erneut.
- Das Nachladen der Hoch-Stufe und des Unterschriftenmodells braucht kaum
  noch Arbeitsspeicher: Das 596-MB-Paket wurde bisher komplett im Speicher
  gehalten, geprüft und dort entpackt – über ein Gigabyte Spitze im laufenden
  Programm, auf Rechnern mit 8 GB der Moment, in dem alles zu stocken begann.
  Jetzt fließt es blockweise auf die Platte und wird dort geprüft und
  entpackt.
- Die Suche im Nachbessern-Editor lässt große PDFs nicht mehr einfrieren:
  Der erste Buchstabe im Suchfeld las bisher alle Seiten auf einmal ein – bei
  200 Seiten stand das Fenster zwei Sekunden, und nach jeder Schwärzung noch
  einmal. Die Seiten werden jetzt häppchenweise gelesen; bis dahin steht
  „Wird gelesen …" im Zähler, das Ergebnis ist dasselbe.
- Gerasterte PDF-Seiten – nach einer Texterkennung oder wenn ein Text nicht
  sauber zu entfernen war – werden deutlich kleiner und ohne Bildverlust
  gespeichert: Statt immer als JPEG wird jede Seite auch verlustfrei kodiert,
  und die kleinere Fassung kommt in die Datei. Ein bereinigter Scan schrumpft
  so von 248 auf 48 KB, das Übungsdokument mit Texterkennung von 913 auf
  702 KB; Text bleibt gestochen scharf.
- Nachgeladene Modelle (Hoch-Stufe, Unterschriften, Gesichter, zweite
  Texterkennung) werden nach zehn Minuten ohne Bereinigung wieder aus dem
  Arbeitsspeicher entlassen. Bisher blieben sie bis zum Programmende geladen
  – wer einmal eine Unterschriftensuche und die Hoch-Stufe benutzt hatte,
  hielt dauerhaft über zwei Gigabyte. Der nächste Lauf lädt sie in ein bis
  zwei Sekunden wieder; die Statuszeile sagt es an.
- PowerPoint: Die Gattungsnamen von Folienlayouts und Folienmastern („Leer",
  „Titelfolie") werden nicht mehr als Angabe ersetzt. „Leer" ist auch ein
  Ort und wurde in jeder deutschen und englischen Präsentation fälschlich
  geschwärzt; bereinigt werden nur noch die von Hand vergebenen Namen der
  Folien selbst.
- In PDFs zieht die Zeilenglättung nicht mehr den Kopf der nächsten Zeile in
  einen Fund: Die Nummer des nächsten Listenpunkts hinter einem Datum galt
  als Rufnummer, ein Feldkopf wie „Kenncode" oder „Auftragsnummer" hinter
  einer Zahl als Postleitzahl mit Ort, und die Ortszeile unter der
  Anschrift verdoppelte den Ort. Der jeweils richtige, kürzere Fund wurde
  dadurch verdrängt. Über 132 Korpus-PDFs bleiben von 24 zusätzlichen
  Glättungsfunden die zwei echten; im Praxiskorpus sinken die Fehlalarme
  von 29 auf 21 bei gleicher Fundquote.
- „PDF-Ordner durchsuchen und schwärzen" im Nachbessern-Editor blockiert das
  Fenster nicht mehr: Der Lauf arbeitet im Hintergrund, Fortschritt und
  Abbrechen-Knopf reagieren, und Menüs oder Reiter können nicht mehr mitten
  in einer halb fertigen Datei bedient werden.
- Gescannte Seiten mit Fundstellen werden beim Schwärzen nur noch einmal
  neu geschrieben statt zweimal: Bisher füllte das Programm die Kästen der
  Fundstellen und die der Begründungen in zwei Durchgängen, und der zweite
  komprimierte das gerade neu gespeicherte Scanbild ein weiteres Mal. Das
  spart Zeit auf großen Scans und einen Qualitätsverlust im Bild.
- Blättern, Zoomen und die Miniaturen im Nachbessern-Editor reagieren
  schneller: Jede gerenderte Seite ging bisher als PNG durch eine Kompression
  und gleich wieder zurück, nur um angezeigt zu werden – bei Bildschirmen mit
  hoher Auflösung rund eine Zehntelsekunde je Seite. Das Bild kommt jetzt
  direkt an, Bildpunkt für Bildpunkt dasselbe.
- Die Sichtprüfung vor dem Speichern einer PDF („Ausgabeprobe") ist rund
  dreimal schneller, bei gleichem Ergebnis.
- Das Hauptfenster steht noch einmal rund eine Viertelsekunde früher: Die
  Prüfung, ob die Texterkennung auf diesem Rechner bereit ist, lief beim
  Fensteraufbau – auf dem Mac samt einer Probe-Anfrage an die
  Systemerkennung – und die Einstellungsseite der Zusatzkomponenten fragte
  dazu den Stand aller 48 Sprachen ab. Beides geschieht jetzt im
  Hintergrund beziehungsweise erst, wenn die Sprachliste wirklich geöffnet
  wird; bis dahin steht „Texterkennung wird geprüft …".
- Nach einer Unterschriftensuche belegt das Programm rund 300 MB weniger
  Arbeitsspeicher: Das Erkennungsmodell lag bis dahin doppelt im Speicher –
  einmal zum Prüfen seiner Echtheit, einmal zum Rechnen. Geprüft wird es
  weiterhin, nur ohne die zweite Kopie.
- Die Texterkennung in PDFs ist spürbar schneller geworden: Für jeden
  Feldkopf einer Seite („Geburtsdatum:", „Steuernummer:") wurde bisher je
  Angabenart eine eigene Probe durch die Erkennung geschickt – auf jeder
  Seite neu, auch wenn derselbe Kopf schon zehn Seiten vorher stand. Die
  Antwort wird jetzt gemerkt; ein zweiseitiges Leistungsverzeichnis stellte
  so 324 Fragen, jetzt noch die verschiedenen. Die Funde sind dieselben.
- Große Tabellen werden wieder in Sekunden statt Minuten bereinigt: Im
  anonymisierenden Betrieb – der Vorgabe – wurde der Abgleich schon bekannter
  Werte mit jeder weiteren Zelle langsamer, weil ein Zwischenspeicher bei
  jedem Treffer verworfen und neu aufgebaut wurde. 5 000 Zellen brauchten
  dafür rund 18 Sekunden, jetzt eine halbe; das Ergebnis ist Zeichen für
  Zeichen dasselbe.
- Das Hauptfenster erscheint noch einmal deutlich schneller: Die Länderliste
  der Einstellungen zog beim Fensterbau die gesamte Erkennungsbibliothek in
  den Vordergrund – rund 0,7 Sekunden auf dem Mac, auf Windows entsprechend
  mehr –, obwohl dafür nur die Namen der Länder gebraucht werden. Die Liste
  kommt jetzt aus einem leichten Katalog; die Bibliothek lädt wie vorgesehen
  im Hintergrund, während das Fenster schon steht. Das gilt auch nach jedem
  Sprach- oder Erscheinungsbildwechsel, der das Programm neu startet.
- Das Dokumentlabor führt angeschnittene Feldköpfe, lokale Wertschatten und
  starke Scanbeschnitte jetzt vollständig durch PDF-, DOCX- und ODT-
  Container. Die Matrix umfasst 680 Dateien aus 40 Dokumentfamilien und 17
  Containerachsen. Maskuro entfernt in den neuen sowie den vollständigen
  Grund- und Merkmalsprofilen alle Sollangaben, ohne gemessenen Fehlalarm,
  beschädigten Erhaltenswert oder Abbruch.

- Mehrfach verwendete Scans werden jetzt über jede sichtbare Platzierung
  geprüft und bereinigt: Das Dokumentlabor teilt dasselbe Bildobjekt über
  verschiedene Seiten, Größen und Drehlagen in PDF und referenziert denselben
  Bildteil mehrfach in DOCX und ODT. Technische ODT-Rahmennamen wie
  „Formularscan klein quer“ gelten nicht mehr als Person; freie Namen und Orte
  mit ähnlichem Anfang bleiben geschützt. Ein allgemeiner Formularrat des
  abschließenden PDF-Seitenlaufs kann auf einer schon unabhängig gelesenen
  Bildfläche keinen großen Adressfehlfund mehr erzeugen. Die 120 neuen
  Container erreichen in Grund- und Merkmalsprofil alle 813 beziehungsweise
  840 Sollangaben ohne Fehlalarm, Erhaltensverletzung oder Abbruch; die
  vollständige 800-Dateien-Merkmalsabnahme bestätigt 5.600/5.600.

- Das deutsche OCR-Labor umfasst jetzt 560 Scans aus 40 Dokumentfamilien.
  Neue Varianten schneiden Feldkopf- und Seitenränder an oder legen einen
  Schatten direkt über einen Wert. Maskuro schützt dabei auch Namen,
  Anschriften, Geburtsdaten, medizinische Schlüssel und beschriftete
  Kennnummern mit teilweise beschädigter Beschriftung. Gleichzeitig werden
  Formularfeldreste, amtliche Überschriften sowie sachliche Rechts- und
  Informationsbegriffe nicht mehr als Personen oder Orte ersetzt. Die
  vollständigen Grund- und Merkmalsprofile erreichen 3.794/3.794
  beziehungsweise 3.920/3.920 Sollangaben ohne gemessenen Fehlalarm oder
  Abbruch.

- Die automatische PDF-Bildauswahl entfernt großflächige Produktfotos,
  Energieetiketten und Porträtreihen nicht mehr allein deshalb, weil sie im
  oberen Seitenrand beginnen. Echte flache Kopf-/Fußbilder und am Blattrand
  ansetzende Briefköpfe fallen weiterhin. In Mitarbeiterverzeichnissen
  werden Namen nun auch dann aus strukturell wiederholten Einträgen erkannt,
  wenn der sichtbare Dokumenttitel nur als Bild vorliegt. Die Erkennung ist
  nicht mehr auf zwei konkrete Rollenwörter und das Kürzel „DW“ zugeschnitten:
  ein bis vier umgebrochene Rollen sowie „Durchwahl“, „Nebenstelle“, „Ext.“
  und „Extension“ werden aus der gemeinsamen Bauform erschlossen. Rollen und
  Abschnittsköpfe bleiben stehen, auch wenn das Sprachmodell nach der
  Überlappungsauflösung nur ein Rollenadjektiv übrig lässt. Waagerechte
  Rollenraster gelten nicht mehr irrtümlich als Namensspalten. Verklebt die
  Seiten-OCR mehrere Karten zu einem extrem breiten Binnen-Großschreibungswort,
  trennt ein enger örtlicher Gegenblick die wirklichen Wortkästen; dadurch
  bleiben weder ein Einzelname noch ein breiter Fehlbalken zurück. Wiederholte
  mehrzeilige Firmenlogos werden anhand einer bereits bestätigten identischen
  Pixelvorlage auch auf Seiten ohne brauchbaren OCR-Text und bei bis zu zwei
  Pixeln Lageabweichung geschwärzt; kürzere lokale Zweitlesungen der OCR dürfen
  zugleich keinen größeren Kopfbereich mehr als erfundenen Namen ergänzen.
  Seitenzahlen vor einem Firmenbriefkopf
  gehören nicht mehr zum Organisationsnamen, numerisch beginnende echte
  Markennamen bleiben geschützt. Mehrere gemessene Produkt-, Fach- und
  Formularwörter werden nicht mehr als Personen vorgeschlagen.

- Die Unterschriftensuche läuft bei PDFs erst nach der OCR-Bildbereinigung,
  besucht auch Seiten ohne gewöhnlichen Texttreffer und rechnet Fundkästen
  gedrehter Seiten korrekt in den Dokumentraum zurück. Dichte Produktfotos
  werden nicht mehr als Unterschrift geschwärzt. Über eindeutig
  beschrifteten Signaturfeldern schließt ein enger Strich-Rückfall dünne
  Modelllücken; leere Linien mit vorgedrucktem Datum lösen ihn nicht aus.
  Reine Scans mit ausschließlich OCR-/Unterschriftenfunden brechen in dieser
  Phase nicht mehr wegen eines erst im Textzweig geladenen Bildschwärzers ab.

- Viele gleichzeitig geöffnete Dokumente bleiben im Nachbessern-Editor
  unterscheidbar: Die Reiter schrumpfen nicht mehr bis auf ein bloßes
  Auslassungszeichen, und ein Listenknopf rechts zeigt alle vollständigen
  Dateinamen untereinander. Reiter lassen sich per Ziehen umsortieren und mit
  ihrem Kreuz aus derselben Liste nehmen wie im Hauptfenster; ungespeicherte
  Arbeit wird dabei weiterhin zuerst geklärt. Ein Rechtsklick bietet außerdem
  „Schließen“, „Andere Reiter schließen“ und „Reiter rechts schließen“.

- Eine kurzzeitige Windows-Sperre durch Virenscanner oder Suchindex lässt den
  fertig geladenen Sprachmodell- beziehungsweise Wörterbuchordner nicht mehr
  beim abschließenden Einsetzen mit „Zugriff verweigert“ scheitern. Maskuro
  versucht diesen letzten Ordnerwechsel nun für kurze Zeit erneut.

- Das deutsche Dokumentlabor prüft Container jetzt auch mit wechselnder
  PDF-Seitendrehung, unabhängig gedrehten PDF-Bildern sowie skalierten und
  zugeschnittenen Tabellenbildern in DOCX und ODT. Feldwerte in sichtbar
  gedrehten Bildern werden wieder vollständig erkannt, technische
  Spaltenbezeichner nicht mehr als Orte ersetzt und Namen mit gemeinsamem
  Familiennamen nicht mehr durch den Konsistenz-Nachpass in doppelte
  Teiltreffer zerlegt. Die auf 320 Dateien verdoppelte Matrix erreicht mit
  zugeschalteter Datum-, Geld- und Medizinerkennung 2.240/2.240 Sollangaben
  ohne gemessenen Fehlalarm oder Abbruch.

- Mehrseitige Bild-PDFs, gemischte Text-/Bild-PDFs und in DOCX oder ODT
  eingebettete Scans werden jetzt in einem eigenen 160-Dateien-Labor über
  alle 40 deutschen Dokumentfamilien geprüft. Technische ODT-Rahmennamen und
  beschriftete Gerätecodes werden nicht mehr als Orte ersetzt; echte Namen,
  Orte und Adressen in denselben Strukturen bleiben geschützt. Mit
  eingeschalteter Medizin- oder Gelderkennung werden außerdem eine direkt
  folgende Dosierung beziehungsweise ein Zahlungsintervall vollständig
  entfernt. Container-, Textgrund-, Textmerkmal- und OCR-Merkmalläufe
  erreichen zusammen ihre jeweiligen Vollstände ohne gemessenen Fehlalarm
  oder Abbruch.

- Die Sicherheitsprüfung vor dem Speichern zeigt auffällige PDF-Stellen nun
  als einzeln anwählbare Liste. „Im Editor prüfen“ öffnet genau die gewählte
  Seite und markiert den Bereich; überlappende Teiltreffer an derselben Stelle
  erscheinen nur noch einmal. Die neuen Bedientexte sind in allen 17
  übersetzten Oberflächensprachen vollständig vorhanden.

- Markdown-Dateien behalten beim Ersetzen ihre Verweis-, Hervorhebungs- und
  Fußnotensyntax. Maskuro liest dafür eine zeichengleich lange Fassung ohne
  Markdown-Markierungen; Unterstriche in E-Mail-Adressen, Rechensterne und
  gewöhnliche Verweise ohne persönliche Angabe bleiben unverändert.

- Mehrere handschriftliche Einträge auf derselben PDF-Seite werden nun in bis
  zu drei Durchgängen gesucht. Bereits gefundene Züge werden nur im
  Arbeitsbild ausgeblendet, damit sie schwächere Unterschriften nicht mehr
  verdrängen; auf gedrehten Seiten landen die Schwärzungsflächen wieder an
  der sichtbaren Fundstelle. Bildfüllungen früherer Sicherheitsphasen bleiben
  beim anschließenden Zurückschreiben erhalten.

- „Alle Einstellungen zurücksetzen“ erfasst jetzt auch „Text in Bildern“.
  Ist die OCR-Komponente nicht verfügbar, bleibt der Schalter technisch aus,
  ohne fälschlich als vom Auslieferungsstand abweichend markiert zu werden.

- Große Bildfragmente am oberen Seitenrand gelten nicht mehr allein wegen
  ihrer Lage als Kopfzeile. Dadurch bleiben insbesondere bildbasierte
  Artikelbeschreibungen und Tabelleninhalte erhalten. Neu erkannte,
  typgenaue E-Mail- und Formularfunde werden außerdem auch auf einer bereits
  geprüften Bildfläche nicht mehr aus der abschließenden Sichtprüfung
  herausgefiltert.

- Technische Positions- und Artikelzeilen in Klima- und Elektroangeboten
  werden enger von Personen, Orten und Organisationen unterschieden. Das
  betrifft unter anderem Kabeltypen, AC-Versorgung, Positionsnummern sowie
  versale Produktcodes; echte Namen und Anschriften bleiben geschützt.

- Die Prüfung realer bereinigter PDFs verwechselt Preisbestandteile wie
  `1 699,59` nicht mehr mit Telefonnummern und schneidet aus einem vollständigen
  Datum wie `08.05.2025` keine vermeintliche Kartenangabe mehr heraus. Namen
  hinter einer Anrede enden am Zeilenumbruch statt in der folgenden Straße;
  Ortsnamen in Beilagen-Dateinamen werden auf den tatsächlichen Ort begrenzt.
  Fahrzeugfarben, technische Statuswerte, Gewerbebezeichnungen und
  Produkt-Rechtsformen bleiben ebenfalls erhalten. Beschädigte
  Platzhalterlesarten wie `|PLLZ` werden bei einem zweiten OCR-Durchgang nicht
  erneut als persönliche Angabe behandelt.

- Seitlich gespeicherte PDF-Bilder erhalten bei der abschließenden
  Sichtprüfung einen zusätzlichen Blick in ihrer unveränderten Bildlage.
  Dieser darf ausschließlich Werte nachschwärzen, die Maskuro auf derselben
  Seite bereits sicher erkannt hat. So wird etwa ein kleiner gedrehter
  Adressstempel vollständig abgedeckt, ohne neue Wörter aus Bildüberschriften
  oder technischen Zeichnungen als persönliche Angaben zu erfinden.

- In OpenDocument-Texten werden die Verfasser-Initialen einer Notiz
  (Kommentar) jetzt zusammen mit dem Verfasser geleert. LibreOffice legt
  sie neben dem vollen Namen als eigene Kurzform ab und zeigt genau diese
  am Seitenrand; bislang stand dort „SO“ weiter, während „Sieglinde
  Ortner“ daneben längst ein Platzhalter war. Geleert wird nur, wenn der
  Verfasser tatsächlich ersetzt wurde – die Notiz einer Abteilung behält
  ihre Kennzeichnung.

- In italienischen Geschäftsbriefen gelten die Standardwendungen am
  Satzanfang nicht mehr als Name oder Ort: „Restiamo a disposizione",
  „Rimaniamo", „Attendiamo", „Alleghiamo", „Comunichiamo" und „Auguriamo
  buon lavoro" blieben bisher als vermeintliche Person oder Ortsangabe
  hängen. Echte Namen an derselben Stelle („Rossi Mario") werden weiterhin
  erkannt.

- Zweispaltige Scans schützen beschriftete Kennungen und Ortsangaben jetzt
  auch dann, wenn die Texterkennung erst alle Feldköpfe und danach alle Werte
  liefert. Die Zuordnung folgt der sichtbaren Pixelzeile und funktioniert
  auch bei um 90 Grad gedrehten Seiten. Eng getrennte Teile einer Pass- oder
  Vertragskennung werden gemeinsam geschwärzt; beschriftete Geburtsdaten,
  ICD- und PZN-Schlüssel sind ebenfalls abgedeckt, nachfolgende Sachwörter
  bleiben stehen. Kurze Namen und Benutzernamen werden an exakten Feldern
  geschützt; in mehrere OCR-Wörter zerlegte E-Mail-Adressen nur bei enger
  Nachbarschaft und vollständiger E-Mail-Grammatik. Eine feldgebundene
  Berichtigung verwechslungsfähiger Zeichen sowie das örtliche Nachlesen
  eines noch leeren Personenfelds schließen beschädigte und gedrehte Scans,
  ohne Sachfelder oder bereits belegte Werte auszuweiten. Sicherheitsränder
  folgen der Wortgröße, und das Merkmalsprofil nimmt unmittelbar
  benachbarte Dosiseinheiten und Zahlungsintervalle mit. Leicht schief
  eingezogene Formulare werden aus mehreren richtungsgleichen OCR-Zeilen
  geometrisch zurückprojiziert; Rundungsrauschen oder widersprüchliche
  Zeugen genügen nicht. Kurze Buchstabenpräfixe bleiben vor einer
  Bindestrichkennung erhalten, und ein vollständiger beschrifteter
  Anschriftsfund ersetzt nur seinen gleichartigen Straßen-Teilfund. Ein
  verlesener Rollenfeldkopf fällt ausschließlich in einer durch mindestens
  drei bekannte Köpfe belegten Formularspalte; Chatnamen bleiben geschützt.
  Ein knapper Randbeschnitt und eine lokale Überbelichtung mit diagonalem
  Lichtreflex ergänzen die Bildmatrix. Über mehrere Formularzeilen reichende
  Personen-, Orts- und Firmenfunde werden in einer mehrfach belegten
  Feldspalte auf den jeweiligen Wert begrenzt. Ein technischer Positionswert
  fällt nur mit Positionskopf und passender Kennform; echte Namen bleiben
  geschützt. Auch am Lichtreflex abgebrochene E-Mail-Werte werden hinter
  einem ausdrücklichen E-Mail-Feldkopf mit engem, nachbarbegrenztem Bildrand
  entfernt. Zwei Feld-Wert-Paare derselben sichtbaren Zeile werden jetzt
  unabhängig ausgewertet; Werte auf einer tieferen Grundlinie nur nach drei
  übereinstimmenden geometrischen Zeugen gekoppelt. Dadurch bleiben
  Kennnummern, Geburtsdaten und Anschriften auch in dichten Formularlayouts
  vollständig geschützt. Straße, PLZ und Ort werden ausschließlich innerhalb
  desselben Adressfelds und mit passender postalischer Grammatik vereinigt.
  Eng umrissene Sachfelder für Arbeits-/Hilfsmittel und Zahnstatus erzeugen
  keine Orts- oder Verzeichnisfehlalarme mehr; echte Namen und ähnlich
  benannte Felder bleiben geschützt. Das deutsche Dokumentlabor umfasst nun
  440 Scans und erreicht 2.981/2.981 im Grundprofil sowie 3.080/3.080 im
  Merkmalsprofil. Alle elf Bildmutationen und alle 40 Dokumentfamilien liegen
  bei 100 Prozent,
  weiterhin ohne gemessenen Fehlalarm, Erhaltensverletzung oder Abbruch.

- PDF-Textschichten mit verlorenen Zelltrennern begrenzen Organisations-,
  Anschrifts- und Ortsfunde jetzt anhand der wiederholten Feld-Wert-Struktur.
  Feldköpfe vor Firmenwerten und technische Pfeile wie `=>` oder `->`
  gehören nicht mehr zum Treffer. Die zusätzliche Ansicht für weiche
  Zeilenumbrüche darf Rechtsform- und Ortsfunde nicht mehr über mehrere
  Tabellenzeilen ausdehnen; eine bereits vollständige Anschrift endet vor
  dem nächsten Feldkopf samt Wert. Der abschließende Lauf über alle 1.600
  TXT-, HTML-, PDF- und DOCX-Dokumente entfernt 10.840/10.840 Sollangaben
  bei null Fehlalarmen, null Erhaltensverletzungen und null Abbrüchen.

## Wie die Fassungen gezählt werden

Es gibt drei Ausgabewege. Wer eine Fassung installiert, bleibt auf dem
gewählten Weg, bis er ihn ausdrücklich wechselt.

| Weg | Für wen | Beispiel |
|---|---|---|
| **Stabil** | den täglichen Einsatz | `1.5.0` |
| **Vorabfassung** | wer Neues früher haben und Rückmeldung geben will | `1.5.0-beta.1` |
| **Tagesfassung** | Erprobung; kann Fehler enthalten | `1.5.0-alpha.20260805` |

Eine Fassung erhält ihre Nummer beim Bauen aus der Versionsverwaltung – sie
wird nicht von Hand gepflegt. Damit können das, was ausgeliefert wird, und das,
was im Programm angezeigt wird, nicht auseinanderlaufen.

**Eine stabile Fassung herausgeben:**

```bash
git checkout main
git tag -a v1.5.0 -m "Fassung 1.5.0"
git push origin main --tags
```

**Eine Vorabfassung:**

```bash
git checkout beta
git tag -a v1.5.0-beta.1 -m "Vorabfassung 1"
git push origin beta --tags
```

Tagesfassungen brauchen keine Marke – sie entstehen aus dem jeweiligen Stand
des Entwicklungszweigs und tragen das Datum im Namen.
