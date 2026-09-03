# Änderungen

Was sich von Fassung zu Fassung ändert – beschrieben aus Sicht der Anwendung,
nicht ihrer Innereien. Wer wissen will, *woraus* sie gebaut ist, findet das in
[LIZENZEN.md](LIZENZEN.md); hier steht, was sich für die Arbeit damit ändert.

Die Nummerierung folgt der üblichen Zählweise: Die **erste** Zahl ändert sich,
wenn etwas nicht mehr so funktioniert wie bisher, die **zweite** bei neuen
Fähigkeiten, die **dritte** bei Fehlerbehebungen.

---

## Unveröffentlicht

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

## 0.10.44-beta.1 – 1. September 2026

- Der Paketbau erzeugt getrennte Ausgaben für Windows x64 und ARM64, macOS
  auf Apple Silicon und Intel sowie Linux x64 und ARM64. Paketnamen,
  Aktualisierungsauswahl und Freigaben unterscheiden die Architektur; eine
  Veröffentlichung bleibt gesperrt, solange eines der sechs Ziele oder sein
  Abhängigkeitsnachweis fehlt. Linux ARM64 setzt wegen Qt mindestens glibc
  2.39 voraus. Vollständig auf echter Hardware abgenommen sind vorerst nur
  Windows x64 und macOS auf Apple Silicon; die übrigen Architekturpakete sind
  klar als Vorabfassungen für Erprobung statt produktiven Einsatz auszuweisen.

- Bei mehreren Dateien arbeitet die Erkennung nun weiter, während eine
  Vorschau auf Durchsicht wartet. Bis zu drei vorbereitete Vorschauen werden
  nacheinander gezeigt; gleichzeitig rechnet weiterhin nur ein Dokument,
  und eine Ergebnisdatei entsteht erst nach ihrer Freigabe. Eine in der
  Vorschau gewählte Dauerausnahme gilt auch für bereits vorbereitete folgende
  Dokumente.

- Redaktionszertifikate lassen sich nun jederzeit direkt im Datei-Menü gegen
  das geschwärzte Dokument prüfen. Maskuro unterscheidet dabei eine passende
  signierte Datei, einen passenden aber unsignierten Beleg, eine ungültige
  Unterschrift und ein nicht zum Zertifikat gehörendes Dokument. Eine Lizenz
  oder das ursprüngliche Betriebssystemkonto ist für die Gegenprobe nicht
  erforderlich.
  Für automatische Prüfstellen steht derselbe Vergleich über
  `--zertifikat-pruefen` bereit; Rückgabecodes unterscheiden Übereinstimmung,
  Bedienfehler und ungültigen Nachweis.
  Die Gegenprobe vergleicht zusätzlich die eingebettete Maskuro-ID mit dem
  Zertifikat; eine frei eingetragene fremde ID fällt dadurch auch bei einem
  unsignierten Beleg auf.
  Bei gültiger Unterschrift zeigt der Prüfbefund außerdem den von der
  Verwaltung aktivierten Bearbeiter mit Betriebssystemkonto, technischer
  Konto-ID und Plattform. Unbestätigte Angaben aus unsignierten oder
  ungültigen Belegen werden nicht ausgegeben.

- Ein neues deutsches Dokumentlabor erzeugt 160 vollständig synthetische
  TXT-, HTML-, PDF- und DOCX-Unterlagen aus zehn Bereichen und vier
  Strukturvarianten. Das Manifest unterscheidet jetzt ausdrücklich zwischen
  Angaben, die verschwinden müssen, und Fachtexten beziehungsweise
  Sachkennungen, die erhalten bleiben müssen; Dokumentfamilie, Mutation und
  öffentliche Strukturquelle sind nachvollziehbar hinterlegt.

- Das deutsche Dokumentlabor wurde auf 280 Dateien, sieben Strukturformen,
  1.540 Sollangaben und 1.036 Erhaltensanker erweitert. Neu geprüft werden
  nummerierte Formulare, geklammerte PDF-/Maskenfelder und technische
  `=>`-Zuordnungen. Der erweiterte Vollstand erreicht in TXT, HTML, PDF und
  DOCX jeweils 100 Prozent bei null Fehlalarmen. Geklammerte Datums- und
  Kennnummernfelder, Pfeiltrenner und ausdrücklich beschriftete Verbände
  werden nun strukturell erkannt.

- Eine zweite Laborerweiterung hebt den Bestand auf 400 Dokumente, zehn
  Strukturformen, 2.200 Sollangaben und 1.480 Erhaltensanker. JSON-artige
  Schlüsselwerte, YAML-Listen und versale Formularfelder erreichen zusammen
  mit dem bisherigen Bestand 100 Prozent bei null Fehlalarmen. Zitierte
  Geburtsdaten und Kennnummern sowie ausdrücklich beschriftete Rollen wie
  versicherte, bewerbende, abgabepflichtige und vertretungsbefugte Personen
  werden nun auch in diesen Exportformen erkannt.

- Ein getrennter OCR-Modus des deutschen Dokumentlabors erzeugt zusätzlich
  200 reine Bildscans aus allen 40 Familien. Saubere, kontrastarme,
  niedrig aufgelöste, JPEG-artefaktbehaftete und um 90 Grad gedrehte Seiten
  werden mit exakten Pixelkästen nachgemessen, ohne den vergleichbaren
  1.600-Dateien-Textgrundstand zu verändern. Das Manifest trennt
  zuschaltbare Datum-, Geld- und Medizinmerkmale vom Grundprofil und kennt
  belegte OCR-Lesarten, ohne sie als zusätzliche Sollstellen zu zählen. Die
  Messung wird nach Mutation und Dokumentfamilie aufgeschlüsselt. Enge
  Feldgrenzen verhindern unter anderem, dass `Az` im Ortsnamen `Graz` ein
  folgendes Datum als Aktenzeichen schwärzt; die aktuelle Grundmatrix läuft
  mit null Fehlalarmen und null Abbrüchen.

- Fünf weitere deutsche Dokumentfamilien für Rechnung/Lieferschein,
  Bank/Kredit, Miete/Hausverwaltung, Schule/Hochschule und Logistik/Zoll
  erweitern das Labor auf 600 Dateien mit 3.520 Sollangaben und 2.360
  Erhaltensankern. Ein enger PDF-Tabellenweg nutzt den ausdrücklichen Kopf
  `Feld Angabe`, wenn der Textlayer Zelltrenner verliert; eine neue
  `--familien`-Auswahl beschleunigt Teilmessungen. Die 200 neuen Dateien
  erreichen 1.320/1.320 bei null Fehlalarmen und null Abbrüchen.

- Versicherung/Schaden, Arbeit/Lohn, Medizin/Labor, Fahrzeug/Werkstatt und
  Technik/Wartung erweitern das deutsche Dokumentlabor auf 800 Dateien mit
  4.960 Sollangaben und 3.200 Erhaltensankern. Eng beschriftete Polizzen-,
  Patienten-, Prüfer- und Fahrzeugkennungen sowie neue Rollen-, Anschrifts-
  und Organisationsfelder werden erkannt. Die neue Teilmatrix und die
  vollständige Matrix erreichen 100 Prozent bei null Fehlalarmen und null
  Abbrüchen in TXT, HTML, PDF und DOCX.

- Bau/Ausschreibung, Energie/Umwelt, Verein/Gesellschaft,
  Kommunikation/Kalender und Hotel/Veranstaltung heben das deutsche
  Dokumentlabor auf 1.200 Dateien mit 7.920 Sollangaben und 4.800
  Erhaltensankern. Neue Rollen-, Firmen-, Anschrifts-, Register-, Vergabe-,
  Buchungs- und Benutzerkontofelder werden auch in allen Exportformen
  erkannt. Zählernummern bleiben als Sachkennungen erhalten. Teil- und
  Vollmatrix erreichen 100 Prozent bei null Fehlalarmen und null Abbrüchen.

- Gastronomie/Lieferdienst, Apotheke/Rezept, Bestattung/Friedhof,
  Sport/Mitgliedschaft und Immobilien/Makler erweitern das deutsche
  Dokumentlabor auf 1.400 Dateien mit 9.360 Sollangaben und 5.640
  Erhaltensankern. Neue Personenrollen, Anschriftenfelder und
  Suchauftragsnummern werden erkannt. Beschriftete Firmennamen mit Rechtsform
  bleiben auch über einen automatischen Zeilenumbruch vollständig geschützt;
  Altersklassen und Fachköpfe werden nicht mehr fälschlich ersetzt. Teil- und
  Vollmatrix erreichen 100 Prozent bei null Fehlalarmen und null Abbrüchen.

- Zahnbehandlung, Fahrschule, Feuerwehr/Einsatz, Energiegemeinschaft und
  Pauschalreise erweitern das deutsche Dokumentlabor auf 1.600 Dateien mit
  10.840 Sollangaben und 6.440 Erhaltensankern. Neue Rollen, Anschriftsfelder
  sowie Behandlungs-, Ausbildungs-, Einsatz-, Energie- und
  Reisevertragskennungen werden strukturell erkannt. Die neue 200-Dateien-
  Teilmatrix erreicht 1.480/1.480; die vollständige Matrix erreicht
  10.840/10.840. Beide bleiben bei null Fehlalarmen und null Abbrüchen.

- Die Vollmessung des Dokumentlabors senkte durch enge amtliche Sachformen
  und Strukturregeln die unnötigen Ersetzungen von 68 auf 0, die ausdrücklich
  gemessenen Erhaltensverletzungen von 23 auf 0 und die Abbrüche von 3 auf 0.
  Die Fundquote stieg zugleich von 91,1 auf 100,0 Prozent; TXT, HTML, PDF und
  DOCX erreichen jeweils 100 Prozent. Allgemeine
  Tabellenköpfe wie `Feld` werden nur in der belegten Folge `Feld`/`Angabe`
  gebremst; ein gleichlautender Nachname bleibt geschützt. Gerichtliche
  Aktenzeichen mit Endbuchstaben, Gleichheitszeichen-Felder,
  `Geburtsdatum des Kindes` und mehrere beschriftete Einzelnamen in derselben
  Zeile werden vollständig erkannt. Word-Tabellen und Vorzeilenfelder nutzen
  ihren Feldkopf als temporären Erkennungskontext; beschriftete
  PDF-Anschriften bleiben auch bei einem satzbedingten Zeilenumbruch
  vollständig geschützt.

- Deutsche Personenmerkmals-, Berufs- und Medizinfelder funktionieren nun
  auch mit Windows-Zeilenumbrüchen. Einbuchstabige Geschlechtsangaben wie
  `Geschlecht`/`w` werden in der Vorzeilenform geschützt. Sachliche
  `Artikel-PZN`-Felder lösen dagegen weder einen Arzneischlüssel- noch einen
  Personenfund aus; echte PZN-, ICD- und ATC-Angaben bleiben erkannt.

- Deutsche Formular- und Nummernfelder sind genauer: „DW.“ funktioniert nun
  auch vor einem weichen Zeilenumbruch, ausdrücklich beschriftete Namen werden
  selbst bei Kleinschreibung entfernt und rein numerische Aktenzeichen ihrer
  richtigen Kennnummer-Art zugeordnet. Umgekehrt gilt eine zufällig
  Luhn-gültige Rechnungs-, Beleg- oder Artikelnummer nicht mehr als
  Kreditkarte. Synthetische HTML- und PDF-Ausgabeproben bestätigen Entfernen
  und Erhalten im fertigen Dokument.
  Kennnummern und Benutzernamen werden außerdem erkannt, wenn ihre
  Beschriftung in der unmittelbar vorherigen Tabellen- oder Formularzeile
  steht; sachliche Belegnummern bleiben auch in dieser Form sichtbar.

- Kennwörter werden nun auch hinter einem alleinstehenden Feldkopf in der
  vorherigen Zeile erkannt. Abschließende Sonderzeichen wie `!` oder `#`
  gehören dabei vollständig zum geschützten Wert. Produkt- und Artikel-PINs
  werden umgekehrt nicht mehr als Karten-PIN maskiert; ausdrückliche
  `PIN`- und `Karten-PIN`-Felder bleiben geschützt.

- Kleingeschriebene Formularwerte werden bei eindeutigen deutschen
  Anschrifts- und `PLZ/Ort`-Feldern nun als Adresse beziehungsweise
  Postleitzahl mit Ort statt nur als allgemeiner Ort ausgegeben. Ebenso
  bleiben kleingeschriebene Firmenwerte wie „beispiel service“ hinter einem
  Firmenfeld vollständig geschützt, ohne das Schlusswort als vermeintlichen
  nächsten Feldkopf abzuschneiden.

- Hilfe, FAQ, Datenschutztext und Website erklären den Herkunftsnachweis nun
  gemeinsam: neutrale Maskuro-ID im Dokument, optionale Zuordnung zum echten
  Betriebssystemkonto nur im örtlichen Prüfprotokoll, Benutzerwechsel über
  Windows/macOS/Linux sowie die Aussagekraft von SHA-256 und Unterschrift.

- Bildbasierte technische Leistungsverzeichnisse werden zurückhaltender
  bereinigt. Eindeutige Sachwörter wie „Abbruchhämmern“, „Deckungsrücklass“,
  „Positionsnummern“, „Einbauplatine“ oder „Terminsituation“ sowie mitten im
  Wort getrennte OCR-Formen gelten nicht mehr als Person oder Ort. Ein reales
  Gemeindeamt-Angebot sank dadurch von 140 auf 90 eindeutige Ersetzungen,
  ohne neue Treffer zu erzeugen; Namen wie Schneider, Lang, Bauer und Hahn
  bleiben ausdrücklich geschützt.

- Weitere Fehlalarme aus realen Angeboten sind behoben: „Digital signiert“
  enthält keine vermeintliche Person mehr, eine BIC wird auch ohne Doppelpunkt
  hinter ihrer Beschriftung erkannt, `15000 Alternativ` gilt nicht als
  Postleitzahl mit Ort, und das EU-Zitat „(VO (EG) 715/2007“ erzeugt keine
  Organisation. Ein Photovoltaikangebot sank dadurch von 26 auf 16
  Ersetzungsvorkommen; echte Namen, Orte und Kontodaten blieben erhalten.

- In Mitarbeiterübersichten werden die Stellvertreter-Abkürzung „Stv.“ und
  eine allein abgespaltene „FACILITY“-Bereichsüberschrift nicht mehr als
  Personenname ersetzt. Die reale 13-seitige Gegenprobe sank von 878 auf 875
  Ersetzungen; Namen, Durchwahlen und die Firmenbezeichnung blieben geschützt.

- Bereinigte PDF-, OpenDocument- und Office-Dateien erhalten eine neutrale
  `MASKURO-…`-Kennung in ihren Dokumenteigenschaften. Prüfbericht und
  signiertes Prüfprotokoll führen dieselbe Kennung sowie SHA-256-Werte von
  Quelle und Ergebnis; das Redaktionszertifikat übernimmt die Kennung aus der
  fertigen Datei. Ein Anwendername kommt weiterhin nur hinzu, wenn die
  Verwaltung das bestehende Anwenderfeld ausdrücklich einschaltet.

- Hauptfenster und Einstellungen sind ruhiger gegliedert: Speichern, Kopieren,
  Details, Kennzahlen und das Löschen eines Erkennungsprofils erscheinen erst,
  wenn die jeweilige Handlung möglich ist. Technische OCR-Sprachkürzel und
  lange Beispiele stehen bei Bedarf im Hinweistext statt dauerhaft in der
  Arbeitsfläche. Die Erkennungsseite passt sich schmaleren Fenstern besser an,
  ohne abgeschnittene Erklärungen oder waagrechten Rollbalken; die Warnung vor
  Klartext in der Ersetzungsliste bleibt dabei sichtbar.

- Die Erkennung schließt weitere deutsche und internationale Kontaktfälle: Telefonnummern werden nun für alle auswählbaren Länderregionen geprüft, ungarische und kroatische Vertragsrollen erfassen auch berufsgleiche Nachnamen vollständig, und nummerierte Ersatzteil-/Materiallisten lösen nicht mehr wegen „Mutter / Flach“ einen Personenfehlalarm aus. Personenfelder mit offensichtlich ziffernhaltigem Sachwert werden nicht als Name übernommen; die maschinenlesbare Passzone (MRZ) lässt sich außerdem über die Gruppe „Kennungen“ gemeinsam an- und abschalten.

- Firmen ohne Rechtsform werden hinter mehrdeutigen Arbeitgeberfeldern besser
  von Personen unterschieden: Namen wie „Huber Handel“, „Müller Logistik“ oder
  „Kowalski Handel“ werden vollständig als Firma erfasst, während
  „Arbeitgeber: Bauer Anna“ weiterhin ein Personenname bleibt. Die automatische
  Länderauswahl berücksichtigt bei französischen Dokumenten weiterhin den
  gesamten französischen Sprachraum einschließlich Luxemburg.

- Erkannte Unterschriften und personenbezogener Text innerhalb eines Bildes wurden bisher immer mit einem schwarzen Rechteck verdeckt – auch wenn für Schwärzungen eine andere Farbe oder ein Muster wie „Regenbogen“ eingestellt war. Diese Bildbereiche übernehmen jetzt ebenfalls die gewählte Schwärzungsdarstellung; die deckende Fläche wird weiterhin direkt in die Bildpunkte geschrieben.

- Die englische Erkennung wurde an elf manuell übersetzten echten Dokumenten nachgemessen und gezielt verbessert: Inventarstatus, technische Angebots- und Webshopfelder sowie Rollen in Mitarbeiterverzeichnissen bleiben sichtbar, „CV“ wird im Vorlagensatz nicht mehr als Rechtsform gelesen, zitierte Schriftarten bleiben erhalten, und Namen in senkrechten Lebenslaufköpfen, mehrseitigen Mitarbeiterlisten, hinter „Account manager“ sowie ziffernbeginnende Firmennamen werden vollständig erkannt. Österreichische Firmenbuchnummern funktionieren nun auch hinter einer englischen Beschriftung; die Kurzform „Customer:“, EAR-Registrierungsnummern und Dienstgebernummern tragen ihren Wert. Maßketten, Kabeltypen, EU-Rechtsverweise, Angebots-Gültigkeitsdaten, Erfüllungsorte, Gerichtsstände, Registergerichte, die Steuerabkürzung „NoVA“, technische Nummern in Reifenlabels sowie Normverweise wie „OVE R6-2“ und „AStV“ erzeugen keinen Fehlalarm mehr. Eine gültige beschriftete IBAN endet sauber vor dem Registrierungsfeld oder der Überschrift der Folgezeile; Anschriften mit Gewerbezonen-Zusatz werden auch aus PDF-Textströmen mit Windows-Zeilenumbrüchen vollständig erkannt. Englische Firmen-Einleitungen und strukturierte Sparkassennamen werden vollständig abgegrenzt. Das Land des Ausgangsdokuments bleibt bei den Sprachfassungen für Postleitzahlen und landesspezifische Kennungen erhalten.

- In Empfänger- und Nachrichtenkopfzeilen konnte das Sprachmodell die ersten zwei Namen einer Kommaliste zu einem einzigen Fund verbinden („Bcc: Huber, Mayer“). Beide Namen werden jetzt einzeln erkannt, ersetzt und im Bericht geführt – ebenso hinter „Sent:“, „Reply:“ und „Fwd:“.

- Der maschinenlesbare Bereich eines Passes oder Ausweises (MRZ) fehlte in der Gruppensteuerung „Was gesucht wird“. Er gehört jetzt zu „Kennungen“ und lässt sich mit dieser Gruppe gemeinsam ein- und ausschalten.

- Wer für Ersatztexte die Vorlage „Regenbogen“ wählt, bekommt jetzt auch geschwärzte Stellen im selben Erscheinungsbild; bisher blieben sie überraschend klassisch schwarz. Die Schwärzungsflächen lassen sich danach weiterhin unabhängig auf eine andere Vorlage umstellen.

- Das Seitenfach des Nachbessern-Editors konnte nach dem Wiederherstellen einer gespeicherten Fensteraufteilung leer bleiben, bis seine Breite von Hand verändert wurde. Die Miniaturen werden jetzt nach dem sichtbaren Fensteraufbau neu angeordnet und stehen sofort mittig im Fach.

- Die farbigen Prüfmarken um Ersatztexte in PDFs blieben je nach Kategorie- und Ampelfarbe kaum sichtbar. Eine helle Unterkontur trennt den Prüfrahmen jetzt zuverlässig vom farbigen Platzhalter und vom Seitenhintergrund.

- Wer im Nachbessern-Editor eine Zeile schwärzt, deren Dokument mit engem Zeilenabstand gesetzt ist (typisch für Angebote und Leistungsverzeichnisse), bekam einen Balken, der in die Oberlängen der Zeile darunter ragte – sie war danach nur noch halb lesbar. Der Balken endet jetzt an der wirklich gezeichneten Schrift der Nachbarzeile; die geschwärzte Zeile selbst bleibt dabei samt ihrer Unterlängen vollständig gedeckt.

- Das Übungsdokument („Hilfe → Übungsdokument öffnen“, auch im Rundgang) führt jetzt jede Erkennungsart vor: Zum erfundenen Brief kommen ein Lichtbild mit erkennbarem Gesicht, eine geschriebene Unterschrift, Beruf und Abteilung, Diagnose und Medikament dazu – neben Firmenname, Betrag und Datum, die schon da waren. Was die Voreinstellung absichtlich stehen lässt, erklärt das Blatt selbst, samt dem Schalter, der es entfernt; das Gesicht auf dem Lichtbild wird ab Werk verpixelt.

- Geldbeträge in der üblichen deutschen Schreibweise mit dem Symbol hinter der Zahl („1.240,00 €“) wurden vom Schalter „Geldbeträge ebenfalls entfernen“ nie gefunden – „1.240,00 EUR“ und „€ 1.240,00“ schon immer. Jetzt werden alle drei Schreibweisen erkannt.

- Die Unterschriftensuche arbeitet jetzt auch auf alleinstehenden Bilddateien: Wer einen Scan als JPG oder PNG bereinigt, bekommt handgeschriebene Unterschriften darin geschwärzt – dieselbe Erkennung, dieselbe Meldung im Bericht wie bei PDF. In Office-Dateien eingebettete Bilder werden weiterhin nicht durchsucht, weil die Erkennung dort gemessen unzuverlässig arbeitet; der Haken heißt deshalb jetzt „PDF und Bilddateien: Handgeschriebene Unterschriften schwärzen“.

- Ein Schwärzbalken konnte bei engem Zeilenabstand sichtbar in die Oberlängen der Zeile darunter ragen und sie halb unlesbar machen – die Balkenhöhe kam aus den Schriftmetriken, nicht aus dem, was wirklich auf dem Papier steht. Der Balken endet jetzt an der tatsächlich gezeichneten Tinte der Nachbarzeile, im Nachbessern-Editor wie in der automatischen Bereinigung. Die eigene Zeile samt Unterlängen bleibt dabei immer ganz gedeckt; überschneiden sich die Zeilen wirklich, bleibt der Balken lieber auf der Nachbarzeile stehen, als etwas freizugeben.

- In einem Mitarbeiterverzeichnis mit Rolle unter dem Namen wurde eine weibliche Leitungsbezeichnung („Anna Berger" mit „Montageleiterin" darunter) mit in die Namensersetzung gezogen – die männliche Form daneben blieb korrekt stehen. Die weiblichen „…leiterin"-Formen (Montage-, Team-, Projekt-, Bau-, Abteilungs-, Betriebs-, Gruppen-, Amtsleiterin) werden jetzt wie ihre männlichen Gegenstücke als Funktionsbezeichnung behandelt; Filial-, Personal- und Vertriebsleitung sind in beiden Formen neu dabei.

- Die zuschaltbare Berufserkennung fand weibliche Leitungsrollen wie „Projektleiterin", „Teamleiterin" oder „Abteilungsleiterin" nicht, ihre männlichen Formen aber schon. Beide Formen zählen jetzt gleichermaßen.

- Im Vorschaufenster klebte auf dem Mac die Mehrfachangabe direkt am Begriff („Anna Musterfrau2ק statt „Anna Musterfrau 2ק). Der Abstand steht wieder.

- Die Vergleichslupe hat einen neuen Knopf neben dem Zoom-Regler: Er legt sie mit einem Druck in voller Breite über das Ergebnis – je halbe Höhe, und das Original im selben Maßstab wie das Dokument (der Lupenzoom springt dafür auf 100 %). Ein zweiter Druck dockt sie wieder klein in die linke Spalte und stellt den vorherigen Lupenzoom wieder her. Der Kringel daneben setzt nur noch den Zoom zurück – sein Hinweistext behauptete bisher fälschlich, er docke auch das Fenster wieder an.

- In der Werkzeugleiste des Nachbessern-Editors ist dem gewählten Werkzeug wieder anzusehen, dass es gewählt ist: Der Knopf des aktiven Werkzeugs trägt eine gefüllte Fläche mit blauem Rand – ebenso jeder andere eingeschaltete Umschaltknopf der Leiste (etwa Vergleichslupe oder Lernmodus). Die Markierung war mit der eigenen Knopfgestaltung vom 29. August verloren gegangen.

- Positionsnummern eines Leistungsverzeichnisses („2.3.3.3, 2.3.3.4, 2.3.3.5" untereinander) wurden für IP-Adressen gehalten und aus dem Ergebnis entfernt; dreistufige Nummern mit jahresähnlichem letzten Glied („2.3.19, 2.3.20") fielen als Kalenderdaten. Eine aufsteigende Nummernfolge am Zeilenanfang gilt jetzt als das, was sie ist – eine Positionsliste; echte Adressen (Netzwerktabellen mit technischem Wortumfeld, Zahlen über 99) und echte Datumsangaben bleiben weiterhin erkannt.

- Nachnamen wie „Müller“, „Fischer“, „Bauer“, „Koch“, „Wagner“, „Schneider“, „Weber“, „Jäger“, „Schmied“, „Becker“, „Schuster“, „Schäfer“ oder „Meister“ blieben in Listen der Form „Nachname, Vorname“ (z. B. „Teilnehmer: Müller, Peter; Nowak, Anna“) im Klartext stehen, weil sie zugleich gebräuchliche Berufsbezeichnungen sind. Sie werden jetzt zuverlässig erkannt.

- Beim Schwärzen einer PDF konnte der Balken in schmalen Tabellenzellen die ganze Zelle mitnehmen: Aus dem Treffer „D-LINK“ in einem Leistungsverzeichnis wurde die komplette Produktbeschreibung daneben entfernt, obwohl die Vorschau nur den Treffer genannt hatte. Der Balken deckt weiterhin ganze Adressblock-Zeilen und Feldbeschriftungen ab, verschluckt aber höchstens so viel Unbeteiligtes, wie er Schützenswertes deckt – die Beschreibung neben dem Treffer bleibt jetzt stehen.

- Nach „Ansicht zurücksetzen“ im Nachbessern-Editor blieb das Seitenfach leer – die Miniaturen der Seiten waren erst nach dem Schließen und Neuöffnen des Fensters wieder zu sehen. Jetzt stehen sie auch direkt nach dem Zurücksetzen da, mittig wie zuvor.

- Der Nachbessern-Editor hat ein viertes Werkzeug: **Entfernen** nimmt den Text unter dem Rahmen ersatzlos heraus – ohne Balken (Schwärzen) und ohne Platzhalter (Ersetzen); die Lücke bleibt sichtbar leer. Es arbeitet wortgenau, liegt ein Bild darunter, wird dessen Grund weiß geräumt, und „Original zurückholen“ macht auch eine ersatzlose Entfernung wieder rückgängig. Eigenes Leisten-Symbol und Fadenkreuz-Abzeichen (Kreuz), eigene Merktaste in allen 18 Sprachen (deutsch F wie entFernen).

- In der PDF-Suchleiste steht „Ordner …“ jetzt rechts neben den Suchoptionen. Seit es neben dem Schwärzen auch das Ersetzen von Treffern gibt, passten fünf Knöpfe bei gewöhnlicher Fensterbreite nicht mehr nebeneinander – der erste wurde gestaucht und sein Text abgeschnitten.

- „Alle Einstellungen zurücksetzen“ setzt jetzt auch den Haken „Rot/Grün durch andere Farben ersetzen“ zurück und vermerkt ihn wie jeden anderen mit „geändert“, wenn er von der Auslieferung abweicht.

- Ersatztexte in PDFs wirken jetzt gleichmäßiger: Wo der volle Platzhalter deutlich kleiner ausfallen müsste als seine Zeile (etwa „[BEG16]“ gequetscht in ein kurzes Wort wie „Das“), steht stattdessen eine Kurzform in Zeilengröße („[B16]“) – gut lesbar statt winzig, und die Nummer fürs Zurückholen trägt beide Schreibweisen. Winzig klein wird ein Platzhalter nur noch, wenn selbst die kürzeste Form keinen Platz findet – das bleibt besser als ein Balken ohne jede Auskunft.

- Ein mehrfarbig gesetzter Ersatztext (Verlauf oder Regenbogen) in einer PDF blieb nur bis zum nächsten Eingriff heil: Jede weitere Ersetzung oder Schwärzung auf derselben Seite konnte bereits gesetzte Platzhalter zu einem unlesbaren, gestauchten Buchstabenstapel zusammenschieben – wer im Editor Wort für Wort ersetzte, sah statt „[BEG17]“ nur noch übereinandergedruckte Zeichen. Einmal gesetzte Platzhalter bleiben jetzt stehen, wie sie gesetzt wurden.

- Der Schalter für dauerhafte Ausnahmen in der Vorschau heißt jetzt „Nie entfernen“ – wie die Liste, in die er einträgt; bisher stand dort „nie wieder“. Die Trefferzeile daneben ist aufgeräumter: Das Info-Symbol „ⓘ“ ist größer und leichter zu treffen, und Kästchen, Ersetzen-Marke und Knopf haben eine gemeinsame Höhe. Der Satz rund um einen Fund nutzt seine angekündigte Breite jetzt wirklich – die bisherige Breitenangabe hatte die Anzeige stillschweigend verworfen, und der Ausschnitt brach weiter als schmaler Streifen um.

- Im Editor sagt der Mauszeiger jetzt, welches Werkzeug wirkt: ein Fadenkreuz zum Zielen, daneben ein kleines Zeichen – Balken für Schwärzen, Tauschpfeile für Ersetzen, Rückgängig-Bogen für Wiederherstellen, Pixelraster für Verpixeln. Die bisherigen Handsymbole entfielen; eine Hand heißt sonst überall „greifen und schieben“. Sie hat jetzt eine passende Aufgabe: Über einem rot hervorgehobenen Wort oder Balken wird der Zeiger zur zeigenden Hand – ein Klick genügt dort.

- „Maximale Erkennung (KI)“ bietet kein herunterladbares, örtliches Sprachmodell mehr an – die Stufe rechnet jetzt ausschließlich über eine unter „Eigene KI anbinden" eingerichtete, eigene KI. Wer bereits einen eigenen Server angebunden hatte, bemerkt keinen Unterschied.

- Die geführte Tour der Vorschau erklärt jetzt auch das Info-Symbol „ⓘ“, das den Satz rund um einen Fund zeigt. Und dieser Satz selbst ist besser lesbar: eine Stufe größere Schrift, mehr Zeilenabstand, feste Breite statt eines schmalen, dicht gedrängten Umbruchs.
- Auch „Datei nachprüfen“, „Erkennungsregeln und eigene Begriffe“, „Text bereinigen“ und „Bild bereinigen“ haben jetzt einen eigenen Rundgang – über einen neuen Knopf „Rundgang durch das Fenster“, da diese vier Fenster keine eigene Menüleiste haben.
- Namen unter neun ukrainischen Vertragsrollen-Beschriftungen blieben bei einem homographen Nachnamen unvollständig erkannt, wenn die Beschriftung allein in ihrer Zeile stand: „Покупець“/„Продавець“ (Käufer/Verkäufer), „Поручитель“/„Боржник“ (Bürge/Hauptschuldner), „Свідок“ (Zeuge), „Орендодавець“/„Орендар“ (Vermieter/Mieter) und „Спадкодавець“/„Спадкоємець“ (Erblasser/Erbe). Die Namen werden jetzt vollständig erkannt.

- Der Kommentar eines benannten Bereichs in einer Excel-Mappe (Namens-Manager, Feld „Kommentar") trug einen darin eingetragenen Namen unverändert weiter. Er wird jetzt genauso bereinigt wie der übrige Inhalt der Mappe.

- Namen unter sieben ungarischen Vertragsrollen-Beschriftungen blieben bei einem homographen Nachnamen ganz unentdeckt: „Bérbeadó“/„Bérlő“ (Vermieter/Mieter), „Vevő“/„Eladó“ (Käufer/Verkäufer), „Kezes“/„Főadós“ (Bürge/Hauptschuldner) und „Tanú“ (Zeuge). Die Namen werden jetzt vollständig erkannt.

- Namen unter der tschechischen Käufer-Beschriftung „Kupující“ blieben bei einem homographen Nachnamen ganz unentdeckt. Der Name wird jetzt vollständig erkannt.

- Namen unter der russischen Vormund-Beschriftung „Опекун“ blieben bei einem homographen Nachnamen ganz unentdeckt. Der Name wird jetzt vollständig erkannt.

- Namen unter sechs weiteren kroatischen Beschriftungen blieben unentdeckt: „Jamac“ (Bürge), „Glavni dužnik“/„Dužnik“ (Hauptschuldner/Schuldner), „Ostavitelj“ (Erblasser), „Nasljednik“ (Erbe/Erbin) und „Vjerovnik“ (Gläubiger). Die Namen werden jetzt vollständig erkannt.

- Eine gespeicherte HTML-Seite mit einer eingebetteten Unterseite im `src`-Attribut eines `<embed>` (statt `data` bei `<object>`) trug personenbezogene Angaben darin unverändert weiter. Sie werden jetzt genauso bereinigt wie bei `<object>`.

- Namen unter fünf dänischen Vertragsrollen-Beschriftungen blieben bei einem homographen Nachnamen unvollständig erkannt, wenn die Beschriftung mit Doppelpunkt vor dem Namen stand: „Arvelader“/„Arving“ (Erblasser/Erbe), „Befuldmægtiget“/„Fuldmagtsgiver“ (Vollmachtnehmer/-geber) und „Værge“ (Vormund). Die Namen werden jetzt vollständig erkannt; die entsprechenden norwegischen Beschriftungen sind zur Absicherung ebenfalls ergänzt.

- Platzhalter in Word- und PowerPoint-Dateien tragen jetzt dieselbe Farbe wie im gewählten Erscheinungsbild (einfarbig, Verlauf, Regenbogen oder je Kategorie) – bisher blieben sie dort in gewöhnlicher Textfarbe, auch wenn PDF-Ergebnisse längst farbig ausfielen.

- „Als Text kopieren" und „Als Markdown kopieren" legen den Klartext des Ergebnisses direkt in die Zwischenablage – zum Einfügen in Chat, Mail oder ein anderes Programm, ohne die Datei erst zu öffnen.

- Namen unter fünf weiteren slowenischen Beschriftungen blieben unentdeckt: „Toženec“ (Beklagter), „Tožnik“ (Kläger), „Zastavitelj“ (Verpfänder), „Zastavni upnik“ (Pfandgläubiger) und „Darovalec“ (Schenker). Die Namen werden jetzt vollständig erkannt.

- Der Verfassername einer nachverfolgten Tabellenzellen-Änderung (eingefügte, gelöschte oder zusammengeführte Zelle in Word) blieb in der Datei stehen, auch wenn derselbe Name als Kommentarverfasser längst entfernt war. Er wird jetzt ebenfalls entfernt.

- Namen unter neun weiteren slowenischen Beschriftungen blieben unentdeckt: „Najemodajalec“/„Najemnik“ (Vermieter/Mieter), „Zapustnik“/„Dedič“ (Erblasser/Erbe), „Upnik“/„Dolžnik“ (Gläubiger/Schuldner), „Glavni dolžnik“ (Hauptschuldner) und „Skrbnik“ (Vormund/Betreuer). Die Namen werden jetzt vollständig erkannt.

- Namen unter fünf slowenischen Beschriftungen blieben unentdeckt: „Izvedenec“ (Sachverständiger), „Kupec“ (Käufer), „Prodajalec“ (Verkäufer), „Naročnik“ (Auftraggeber) und „Izvajalec“ (Auftragnehmer). Die Namen werden jetzt vollständig erkannt.

- Namen unter fünf weiteren litauischen Beschriftungen blieben unentdeckt: „Užsakovas“ (Auftraggeber), „Vykdytojas“ (Auftragnehmer), „Vežėjas“ (Frachtführer), „Siuntėjas“ (Absender) und „Arbitras“ (Schiedsrichter). Die Namen werden jetzt vollständig erkannt.

- Namen unter sechs weiteren litauischen Beschriftungen blieben unentdeckt: „Įgaliotinis“ (Vollmachtnehmer), „Įgaliotojas“ (Vollmachtgeber), „Naudos gavėjas“ (Begünstigter, Versicherung), „Trečiasis asmuo“ (Nebenintervenient/Dritte Partei im Zivilprozess), „Ankstesnis nuomininkas“ (Vormieter) und „Naujasis nuomininkas“ (Nachmieter). Die Namen werden jetzt vollständig erkannt.

- Ein Lesezeichen in ODT-Dokumenten (`text:bookmark`) trägt seinen Namen frei vergeben, oft nach der Stelle benannt, auf die es zeigt (z. B. „Herr_Mueller_Unterschrift“) – unsichtbar für den Leser, aber wörtlich in der Datei. Der Name wird jetzt mitbereinigt.

- Namen unter acht weiteren litauischen Beschriftungen blieben unentdeckt: „Pareiškėjas“ (Antragsteller), „Suinteresuotas asmuo“ (Antragsgegner im Nichtstreitverfahren), „Ekspertas“ (Sachverständiger/Gutachter), „Bankroto administratorius“ (Insolvenzverwalter), „Valdybos narys“ (Aufsichtsratsmitglied), „Direktorius“ (Geschäftsführer), „Palikėjas“ (Erblasser) und „Įpėdinis“ (Erbe). Die Namen werden jetzt vollständig erkannt.

- Namen unter sieben weiteren litauischen Beschriftungen blieben unentdeckt: „Liudytojas“ (Zeuge), „Vertėjas“ (Dolmetscher/Übersetzer), „Notaras“ (Notar), „Dovanotojas“ (Schenker), „Apdovanotasis“ (Beschenkter), „Pirkėjas“ (Käufer) und „Pardavėjas“ (Verkäufer). Die Namen werden jetzt vollständig erkannt.

- Namen unter sechs weiteren litauischen Beschriftungen blieben unentdeckt: „Globėjas“ (Vormund/Betreuer), „Palikimo administratorius“ (Nachlassverwalter), „Laiduotojas“ (Bürge), „Pagrindinis skolininkas“ (Hauptschuldner), „Nuomotojas“ (Vermieter) und „Nuomininkas“ (Mieter). Die Namen werden jetzt vollständig erkannt.

- Ein Name unter der litauischen Beschriftung „Ieškovas“/„Atsakovas“ (Kläger/Beklagter als Prozesspartei) blieb unentdeckt, unabhängig davon, ob der Nachname zugleich ein gebräuchliches Wort war (z. B. „Vilkas“ = Wolf) oder nicht. Der Name wird jetzt vollständig erkannt.

- Ein Personenverzeichnis-Eintrag in ODT-Dokumenten (Textmarke fürs Stichwortverzeichnis) trug den Namen ein zweites Mal in seinem eigenen Sortierschlüssel – unsichtbar im Fließtext, aber wörtlich im später erzeugten Verzeichnis. Der Schlüssel wird jetzt mitbereinigt.

- Der Foliennamen und der Abschnittsname einer PowerPoint-Präsentation (sichtbar im Auswahlbereich bzw. in der Foliensortierung) blieben unbereinigt, weil beide als Attribut an einem Element hängen, das kein Folientext ist. Beide werden jetzt erkannt.

- Ein litauischer Bindestrich-Doppelname wie „Petraitis-Kazlauskas“ verlor seine zweite Hälfte, sobald irgendein Fließtext davorstand (nur am Textanfang blieb er vollständig): Der Nachname wird jetzt auch dann ganz erkannt.

- Ein Name unter der Beschriftung „Cesionar“ (kroatisch, Zessionar bei der Forderungsabtretung) erzeugte einen Fehlalarm, weil die Feldbeschriftung selbst fälschlich als Person gelesen wurde. Ein Name unter der russischen Beschriftung „Цессионарий“ (ebenfalls Zessionar) blieb dagegen ganz unentdeckt. Beide Fälle sind jetzt behoben.

- Ein Name unter der Beschriftung „Zedent“/„Zessionar“ (deutsch, Forderungsabtretung) blieb ersatzlos unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Bauer“). Der Name wird jetzt vollständig erkannt.

- Ein Name unter der Beschriftung „Darczyńca“/„Obdarowany“ (polnisch, Schenker/Beschenkter im Schenkungsvertrag) blieb unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Wilk“ = Wolf). Ebenso blieb die rumänische Beschriftung „Donatar“ (Beschenkter) bei einem gewöhnlichen Nachnamen selbst als vermeintlicher Namensbestandteil hängen. Beide Fälle sind jetzt behoben.

- Ein Name unter der Beschriftung „Wierzyciel“/„Dłużnik“ (polnisch, Vollstreckungsgläubiger/Vollstreckungsschuldner bzw. allgemeiner Gläubiger/Schuldner) blieb unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Wilk“ = Wolf). Der Name wird jetzt vollständig erkannt.

- Ein Name unter der Beschriftung „Poręczyciel“/„Dłużnik główny“ (polnisch, Bürge/Hauptschuldner in Bürgschaftsverträgen) blieb unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Wilk“ = Wolf). Der Name wird jetzt vollständig erkannt.

- Ein Name unter der Beschriftung „Ubezpieczony“/„Ubezpieczający“ (polnisch, Versicherter/Versicherungsnehmer in Versicherungspolicen) blieb teilweise oder ganz unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Wilk“ = Wolf). Ebenso ein Name unter „Osiguranik“/„Osiguravatelj“ (kroatisch, dieselben Rollen), dort verschwand er samt Vorname vollständig (z. B. „Golub“ = Taube). Beide Namen werden jetzt vollständig erkannt.

- Ein Name unter der Beschriftung „Pełnomocnik“/„Mocodawca“ (polnisch, Bevollmächtigter/Vollmachtgeber in Vollmachtsurkunden) blieb unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Wilk“ = Wolf). Ebenso ein Name unter „Opunomoćenik“/„Opunomoćitelj“ (kroatisch, dieselben Rollen), dort verschwand er sogar vollständig samt Vorname. Beide Namen werden jetzt vollständig erkannt.

- Ein Name unter der Beschriftung „Pozwany“ (polnisch, Beklagter als Prozesspartei) blieb unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Wilk“ = Wolf). Der Name wird jetzt vollständig erkannt.

- Ein Name unter der Beschriftung „Najmoprimac“/„Najmodavac“ (kroatisch, Mieter/Vermieter in Mietverträgen) blieb unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Kovač“ = Schmied). Der Name wird jetzt vollständig erkannt.

- Ein Name unter der Beschriftung „Pracodawca“/„Pracownik“ (polnisch, Arbeitgeber/Arbeitnehmer als Vertragspartei in Arbeitsverträgen) blieb teilweise unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Krawiec“ = Schneider). Der Name wird jetzt vollständig erkannt.

- Ungarn hatte im Länderkatalog nur die Personenkennungen und die Umsatzsteuer-ID: Die Handelsregisternummer (Cégjegyzékszám) wird jetzt erkannt, sofern das Feldwort „Cégjegyzékszám“ oder die Abkürzung „Cg.“ unmittelbar davorsteht – die Nummer selbst trägt keine Prüfziffer.

- Estland hatte im Länderkatalog nur den Isikukood: Die Käibemaksukohustuslase number (Umsatzsteuer-ID auf jeder estnischen Rechnung) wird jetzt mit Prüfziffer erkannt.

- Lettland hatte im Länderkatalog nur den Personenkode: Die PVN reģistrācijas numurs juristischer Personen (Unternehmenskennung auf jeder lettischen Rechnung) wird jetzt mit Prüfziffer erkannt.

- Eine E-Mail mit verschlüsseltem Inhalt (S/MIME- oder PGP/MIME-Umschlag, `multipart/encrypted`) wurde ohne jede Warnung als scheinbar vollständig geprüft ausgegeben, obwohl ihr eigentlicher Inhalt verschlüsselt und damit ungeprüft blieb. Solche Mails weisen jetzt wie ein ungeprüfter Anhang darauf hin.

- Malta fehlte im Länderkatalog: Die maltesische Umsatzsteuer-ID (VAT number) wird jetzt erkannt.

- Luxemburg fehlte im Länderkatalog: Die luxemburgische Umsatzsteuer-ID (n° TVA) wird jetzt erkannt.

- Ein satzanfangsgestelltes bulgarisches „Изчакайте“ ("Warten Sie!") wurde als Ortsangabe gemeldet – dieselbe Modellgrenze wie zuvor bei ungarischen, polnischen, tschechischen und anderen Aufforderungsformen ohne eigenes Sprachmodell. Der Fehlalarm bleibt jetzt aus.

- Ein Name unter der Beschriftung „Zleceniodawca“, „Zleceniobiorca“ (polnisch), „Prestator“ (rumänisch), „Naručitelj“ oder „Izvođač“ (kroatisch) blieb teilweise oder ganz unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Wilk“, „Vuk“ = Wolf, „Vulpe“ = Fuchs, „Sokol“ = Falke). Der Name wird jetzt vollständig erkannt.

- Ein Name unter der Beschriftung „Nadawca“ (polnisch), „Afsender“ (dänisch) oder „Pošiljatelj“ (slowenisch) blieb teilweise oder ganz unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Sowa“ = Eule, „Bager“ = Bäcker, „Volk“ = Wolf). Der Name wird jetzt vollständig erkannt.

- Ein Name unter der Beschriftung „Gavėjas“ (litauisch) oder „Prejemnik“ (slowenisch) blieb teilweise oder ganz unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Vilkas“ = Wolf). Wie schon bei „Primatelj“ (kroatisch) und „Modtager“ (dänisch) wird der Name jetzt vollständig erkannt.

- Eine Rundschreiben-Kopfzeile wie „To All Staff" oder „To All Employees" wurde fälschlich als Personenname erkannt und entfernt. Das kommt jetzt nicht mehr vor.

- Ein Name unter der Beschriftung „Primatelj“ (kroatisch) oder „Modtager“ (dänisch) blieb teilweise unentdeckt, wenn der Nachname zugleich ein gebräuchliches Wort war (z. B. „Golub“ = Taube, „Bager“ = Bäcker). Wie schon bei „Odbiorca“ (polnisch) und „Destinatar“ (rumänisch) wird der Name jetzt vollständig erkannt.

- Ein vollständiger Name in der Unterschriftszeile eines dänischen, norwegischen oder griechischen Dokuments blieb teilweise unentdeckt, wenn die Beschriftung „Underskrift“ oder „Υπογραφή“ allein über dem Namen stand – im griechischen Fall wurde der Nachname sogar als Ortsangabe statt als Name erkannt. Wie schon bei „Подпись“ (russisch) wird der Name jetzt vollständig erkannt.

- Text auf einem seitlich abgelegten Telefonfoto (die übliche Hochkant-Aufnahme, die nur über eine Bilddrehmarke aufrecht angezeigt wird) konnte von der Texterkennung übersehen werden, weil sie bislang die rohen, liegenden Bildpunkte las. Solche Fotos werden jetzt vor dem Lesen richtig herum gedreht – wie schon zuvor bei der Gesichtserkennung.

- Ein vollständiger Name in der Unterschriftszeile eines russischen, ukrainischen oder litauischen Dokuments blieb teilweise unentdeckt, wenn die Beschriftung „Подпись“, „Підпис“ oder „Parašas“ allein über dem Namen stand – Vor- oder Vatersname fielen weg. Wie schon bei „Potpis“ (kroatisch) wird der Name jetzt vollständig erkannt.

- Ein Gesicht auf einem seitlich abgelegten Telefonfoto (die übliche Hochkant-Aufnahme, die nur über eine Bilddrehmarke aufrecht angezeigt wird) konnte von der Gesichtserkennung übersehen werden, weil sie bislang die rohen, liegenden Bildpunkte prüfte. Solche Fotos werden jetzt vor der Suche richtig herum gedreht.

- Ein vollständiger Name in der Unterschriftszeile eines kroatischen Dokuments blieb teilweise unentdeckt, wenn die Beschriftung „Potpis“ allein über dem Namen oder mit Doppelpunkt davor stand – der Vorname fiel weg, egal ob als eigene Zeile oder in „Potpis: Vorname Zweitname Nachname“. Wie schon bei „Unterschrift“ und „Signature“ wird der Name jetzt vollständig erkannt.

- Ein Ehename hinter den Personenstandsabkürzungen „verh." (verheiratete/verheirateter) und „verw." (verwitwete/verwitweter) blieb bislang vollständig unentdeckt stehen, egal ob in Klammern, hinter Komma oder ohne Leerzeichen angeklebt („Anna Meier (verh. Weber)", „Klaus Bauer (verw.Fischer)") – wie schon bei „geb." wird er jetzt zuverlässig erkannt.

- Ein Name hinter der Prokura-Zeichnung „ppa." (z. B. in der Signaturzeile einer Geschäfts-E-Mail oder eines Geschäftsbriefs) blieb bei einem berufsnamengleichen Nachnamen wie „Bauer" oder „Koch" bislang teilweise oder ganz unentdeckt stehen – wie schon bei „gez." wird er jetzt zuverlässig erkannt.

- Die Nummer des polnischen Personalausweises (dowód osobisty) wurde nur ohne Leerzeichen zwischen Serie und Nummer erkannt („ABS123456"). Genau so druckt das Dokument die Angabe aber nicht – amtlich steht dort ein Leerzeichen dazwischen („ABS 123456"), und in dieser Schreibweise blieb die Nummer bislang unentdeckt.

- Ein animiertes PNG (APNG, z. B. eine als PNG statt GIF abgelegte kurze Bildschirmaufnahme) wurde bislang nur mit seinem ersten Bild geprüft und bereinigt, ohne dass dies gemeldet wurde – wie zuvor beim animierten WebP meldet Maskuro jetzt, dass jedes weitere Bild ungeprüft im Ergebnis stehen bleibt.

- Ein animiertes WebP-Bild (z. B. aus einem Screenshot-Werkzeug oder einer Chat-Anwendung mit mehreren Bildern in einer Datei) wurde bislang nur mit seinem ersten Bild geprüft und bereinigt, ohne dass dies gemeldet wurde – wie zuvor bei einem mehrseitigen TIFF meldet Maskuro jetzt, dass jedes weitere Bild ungeprüft im Ergebnis stehen bleibt.

- Ein slowenischer Doppel-Vorname mit Bindestrich („Ana-Marija Novak") verlor seine vordere Hälfte, sobald ihm im Text ein Fließsatz voranging - derselbe Fehler wie zuvor bei Polnisch. „Ana-" blieb unbelegt im Klartext stehen, während der Rest des Namens bereits ersetzt wurde.

- Ein polnischer Doppel-Vorname mit Bindestrich („Anna-Maria Kowalska") verlor seine vordere Hälfte, sobald ihm im Text ein Fließsatz oder eine Präposition wie „z"/„od" voranging - der Rest des Namens wurde ersetzt, „Anna-" blieb unbelegt im Klartext stehen.

- Kasachische Höflichkeitsformen „Хабарласыңыз“/„Байланысыңыз“ (kontaktieren Sie uns) sowie serbische Verbformen „Помоћи“, „Чекамо“ und „Пишите“ ohne eigenes Spracherkennungsmodell wurden in Telefon-Sätzen fälschlich als Personenname oder Ort erkannt.

- Aserbaidschanisches Höflichkeitswort „Xahiş“ (Bitte/Ersuchen) ohne eigenes Spracherkennungsmodell wurde in Telefon-Sätzen fälschlich als Personenname erkannt.

- Indonesische und malaiische Höflichkeits-/Aufforderungswörter ohne eigenes Spracherkennungsmodell wie „Silakan“, „Mohon“ (indonesisch), „Sila“ und „Tolong“ (malaiisch) wurden in Telefon-Sätzen fälschlich als Personenname oder Ort erkannt.

- Usbekische Aufforderungsform „Kutamiz“ (wir warten) ohne eigenes Spracherkennungsmodell wurde in Telefon-Sätzen fälschlich als Ort erkannt.

- Türkische Aufforderungsformen ohne eigenes Spracherkennungsmodell wie „Arayınız“ (rufen Sie an) und „Bekliyoruz“ (wir warten) wurden in Telefon-Sätzen fälschlich als Personenname erkannt.

- Aufforderungsformen in weiteren Sprachen ohne eigenes Spracherkennungsmodell (Tschechisch, Slowakisch, Griechisch) wie „Zavolejte“ (ruf an), „Prosíme“ (wir bitten) und „Περιμένουμε“ (wir warten) wurden in Telefon-Sätzen fälschlich als Personenname oder Ort erkannt.

- Ungarische und polnische Aufforderungsformen wie „Hívjon“ (ruf an), „Kérjük“ (wir bitten), „Várjuk“ (wir erwarten), „Zadzwoń“ (ruf an) und „Czekamy“ (wir warten) wurden in Telefon-Sätzen fälschlich als Personenname oder Ort erkannt.

- In einer nummerierten Namensliste ohne Tabellenform (z. B. „1. Robert Brown“, darunter „2. Mary Johnson“) wurde ein Name mit bestimmten englischen Nachnamen (u. a. „Brown“, „White“, „Green“, „Black“, „Young“) komplett übersehen – das Sprachmodell hatte die Nummer der folgenden Zeile an den Namen angehängt, wodurch der Treffer nie mehr exakt passte.

- Beim polnischen Sprachmodell blieb der vorangestellte Vornamens-Initial vor einem Nachnamen (z. B. „J. Kowalski“, „A. Nowak“) unerkannt und unbereinigt im Text stehen – nur der Nachname wurde ersetzt. Andere geprüfte Sprachen (u. a. Deutsch, Englisch, Rumänisch, Kroatisch, Ungarisch, Russisch) nahmen denselben Initial schon vorher mit.

- Ein Personenname hinter einem kleingeschriebenen Titel wie „dr.“, „ing.“
  oder „dipl. ing.“ wurde auf Ungarisch, Rumänisch und Kroatisch gar nicht
  erkannt – nicht nur der Titel, sondern der ganze Name ging verloren
  (z. B. „dr. Kovács Béla“, „ing. Andrei Popescu“, „dipl. ing. Marko
  Horvat“).
- In slowenischen Sitzungsprotokollen wurde eine reine Rollenbezeichnung vor dem Doppelpunkt (z. B. „Tajnik:“, „Podpredsednik:“, „Poročevalec:“, „Predsedujoči:“) fälschlich als Personenname erkannt, sobald an anderer Stelle im Protokoll bereits ein echter Sprechername stand.
- In russischen Sitzungsprotokollen wurde eine reine Rollenbezeichnung vor dem Doppelpunkt (z. B. „Секретарь:“, „Докладчик:“, „Докладчица:“) fälschlich als Personenname erkannt, sobald an anderer Stelle im Protokoll bereits ein echter Sprechername stand.
- In rumänischen Sitzungsprotokollen wurde eine reine Rollenbezeichnung mit bestimmtem Artikel vor dem Doppelpunkt (z. B. „Secretarul:“, „Președintele:“, „Vicepreședintele:“, „Moderatorul:“, „Consilierul:“) fälschlich als Personenname erkannt – „Președintele“ schon für sich allein, die übrigen zusätzlich, sobald an anderer Stelle im Protokoll bereits ein echter Sprechername stand.
- In kroatischen Sitzungsprotokollen wurde eine reine Rollenbezeichnung vor dem Doppelpunkt (z. B. „Izvjestiteljica:“, „Zapisničar:“/„Zapisnicar:“, „Predsjedavajući:“) fälschlich als Personenname erkannt.
- Eine polnische Postfach-Anschrift „Skrytka pocztowa“ hinter einer
  Absender- oder Empfänger-Beschriftung (z. B. „Odbiorca: Skrytka
  pocztowa 45“) wurde fälschlich als Personenname erkannt.
- Eine kroatische Postfach-Anschrift „Poštanski pretinac“ hinter der
  Adress-Beschriftung „Adresa:“ (z. B. „Adresa: Poštanski pretinac
  45“, auch mit angehängtem „br.“ für die Nummer) wurde fälschlich
  als Personenname erkannt.
- Ein Ort ohne weitere Beschriftung in norwegischem Fließtext (z. B. „Anna Hansen bor i Oslo“) wurde nicht erkannt – das eigene Sprachmodell benennt Orte dort meist mit einem eigenen, bisher nicht zugeordneten Etikett statt des üblichen „LOC“.
- Ein Datum in der ISO-Reihenfolge Jahr-Monat-Tag mit Bindestrich oder
  Punkt (z. B. „2024-12-31“) wurde in manchen Sprachen gar nicht als
  Datum erkannt – am auffälligsten auf Litauisch, wo amtliche Schreiben
  Daten überwiegend in dieser Reihenfolge angeben.
- Eine ungarische Umsatzsteuer-ID (közösségi adószám) in der amtlich
  ebenso gültigen, trennerlosen 11-stelligen Form (z. B.
  „12345678123“ statt „12345678-1-23“) wurde nicht erkannt.
- Eine polnische Steuernummer NIP mit den Trennern in der Gruppierung 3-2-2-3
  (z. B. „856-73-46-215“, wie sie auf Rechnungen von Unternehmen und
  Einzelunternehmern üblich ist) wurde nicht erkannt – nur die Gruppierung
  3-3-2-2 für natürliche Personen traf.
- Ein Firmenname unter der slowakischen Feldbeschriftung
  „Zamestnávateľ:“ oder „Názov zamestnávateľa:“ (Arbeitgeber/Firma) wurde
  nicht erkannt.
- Ein Firmenname unter der rumänischen Feldbeschriftung
  „Angajator:“ oder „Denumire angajator:“ (Arbeitgeber/Firma) wurde nicht
  erkannt.
- Ein Firmenname unter der ungarischen Feldbeschriftung
  „Cég:“ oder „Munkáltató:“ (Firma/Arbeitgeber) wurde nicht
  erkannt.
- Ein Firmenname unter der polnischen Feldbeschriftung
  „Pracodawca:“ oder „Nazwa firmy:“ (Arbeitgeber/Firma) wurde nicht
  erkannt.
- Ein Firmenname unter der slowenischen Feldbeschriftung
  „Podjetje:“ oder „Delodajalec:“ (Firma/Arbeitgeber) wurde nicht
  erkannt.
- Ein Firmenname unter der kroatischen Feldbeschriftung
  „Tvrtka:“ oder „Poslodavac:“ (Firma/Arbeitgeber) wurde nicht
  erkannt.
- Ein ausgeschriebener Geldbetrag mit klein geschriebener Währung (z. B.
  „500 euro") wurde nicht erkannt, nur die Großschreibung („Euro") traf.
- Der Nachname hinter „Schwager"/„Schwägerin" (z. B. „Der Schwager Bauer
  erhält die Erbschaft.") wurde nicht erkannt.
- Bei einer türkischen Anschrift ohne trennendes Satzzeichen zwischen
  Postleitzahl+Ort und Straße+Hausnummer (z. B. „34000 İstanbul İstiklal
  Caddesi No: 45") blieb die Hausnummer unbereinigt stehen.
- Bei einer slowakischen Anschrift ohne trennendes Satzzeichen zwischen
  Postleitzahl+Ort und Straße+Hausnummer (z. B. „831 01 Bratislava Hlavná
  15") blieb die Hausnummer unbereinigt stehen.
- Ein Geburtsland ohne weitere Beschriftung in einem kroatischen
  Formularfeld (z. B. „Zemlja rođenja: Njemačka") wurde nicht erkannt.
- Ein Geburtsland ohne weitere Beschriftung in einem litauischen
  Formularfeld (z. B. „Gimimo valstybė: Vokietija") wurde nicht erkannt.
- Ein Geburts- oder Wohnsitzland ohne weitere Beschriftung in einem
  polnischen Formularfeld (z. B. „Kraj: Niemcy“) wurde nicht erkannt.
- Ein Staatsangehörigkeits- oder Wohnsitzort ohne weitere Beschriftung in
  einem slowenischen Formularfeld (z. B. „Državljanstvo: Nemčija") wurde
  nicht erkannt.
- Ein Wohnsitzland ohne weitere Beschriftung in einem norwegischen
  Formularfeld (z. B. „Bosted: Tyskland“) wurde nicht erkannt.
- Neue Einstellungsseite „Benachrichtigungen" (vorher ein Abschnitt in „Programm"): die drei Taskleisten-Meldungen (Vorschau bereit, Verarbeitung fertig, Aktualisierung heruntergeladen) stehen jetzt an einem eigenen Ort.
- Neu: Das Ergebnis kann zusätzlich als reine Textdatei (.txt) oder mit der Endung .md daneben abgelegt werden – zum Weiterverarbeiten in einer KI oder einem anderen Programm.
- Bei einer kroatischen Kontaktangabe mit der Beschriftung „Osoba za kontakt“/„Kontakt osoba“ (z. B. „Osoba za kontakt: Golub Marko“) blieb der Name vollständig unerkannt, wenn der Nachname zugleich ein gebräuchliches Substantiv war (Golub = „Taube“).

- Bei einer rumänischen Kontaktangabe mit der Beschriftung „Persoana de contact“/„Persoană de contact“ (z. B. „Persoana de contact: Lup Ion“) blieb der Name vollständig unerkannt, wenn der Nachname zugleich ein gebräuchliches Substantiv war (Lup = „Wolf“) und der Vorname sehr kurz und generisch.

- Bei einer polnischen Kontaktangabe mit der Beschriftung „Osoba
  kontaktowa“/„Osoba do kontaktu“ (z. B. „Osoba kontaktowa: Wilk
  Adam“) blieb der Nachname unerkannt, wenn er zugleich ein
  gebräuchliches Substantiv war (Wilk = „Wolf“, Zielony = „grün“).

- Bei einer rumänischen Anschrift ohne trennendes Satzzeichen zwischen
  Postleitzahl+Ort und Straße+Hausnummer (z. B. „010061 București Strada
  Victoriei 30") blieb die Hausnummer unbereinigt stehen.
- Bei einer serbischen Anschrift ohne trennendes Satzzeichen zwischen
  Postleitzahl+Ort und Straße+Hausnummer (z. B. „11000 Beograd Bulevar
  Kralja Aleksandra 73") blieb die Hausnummer unbereinigt stehen.
- Bei einer griechischen Anschrift ohne trennendes Satzzeichen zwischen
  Postleitzahl+Ort und Straße+Hausnummer (z. B. „104 32 Αθήνα Ερμού 15")
  blieb die Hausnummer unbereinigt stehen.
- Bei einer slowenischen Anschrift ohne trennendes Satzzeichen zwischen
  Postleitzahl+Ort und Straße+Hausnummer (z. B. „1000 Ljubljana Slovenska
  cesta 58") blieb die Postleitzahl unbereinigt stehen.
- Bei einer litauischen Anschrift ohne trennendes Satzzeichen zwischen
  Postleitzahl+Ort und Straße+Hausnummer (z. B. „LT-01100 Vilnius
  Gedimino pr. 9") blieb die Postleitzahl vollständig unbereinigt stehen.
- Bei einer ungarischen Anschrift ohne trennendes Satzzeichen zwischen
  Postleitzahl+Ort und Straße+Hausnummer (z. B. „1052 Budapest Kossuth
  Lajos utca 12") blieb die Postleitzahl unbereinigt stehen.
- Ein Nachname hinter „Erben" (z. B. „Die Erben Wagner erhielten die
  Mitteilung fristgerecht.") blieb im Erbschafts-/Nachlasskontext so gut
  wie immer unerkannt.
- Ein Nachname hinter „Geschwister" (z. B. „Die Geschwister Bauer wohnen
  in Linz.") blieb bislang so gut wie immer unerkannt – anders als bei
  „Familie"/„Ehepaar" traf das nicht nur berufswortgleiche Namen (Koch,
  Bauer, Richter), sondern beliebige Nachnamen an dieser Stelle.
- Ein Nachname hinter „Ehepaar" oder „Eheleute" (z. B. „Das Ehepaar Koch
  zieht um.") blieb unerkannt, wenn er zugleich ein gebräuchliches
  Substantiv oder eine Berufsbezeichnung war (Koch, Bauer, Richter).
- Eine gewöhnliche Bestell-, Auftrags- oder Artikelnummer im typischen
  Gruppierungsraster einer Steuernummer oder Sozialversicherungsnummer
  (z. B. „030 4471 2298") wurde ohne jede zugehörige Beschriftung
  fälschlich als solche geschwärzt.
- Eine Beleg-/Vorgangsnummer im Format „Jahr/laufende Nummer" (z. B. in
  „Rechnung Nr. 4/2024/778899") wurde von der Rufnummer-Erkennung fälschlich
  als Telefonnummer geschwärzt.
- Ein Name hinter „Herr"/„Frau" mit einer mehrwortigen akademischen
  Titelkette davor („Herr Dr. med. Weber", „Herr Prof. Dr. Krause") blieb
  bislang vollständig ungeschützt stehen – erkannt wurde bisher nur ein
  einzelnes Titelwort zwischen Anrede und Namen.
- Ein gerichtliches Aktenzeichen im klassischen Format mit Kammer-/Senats-
  kürzel („4 Ca 1523/24", „Az.: 7 O 234/25") blieb bislang vollständig
  ungeschützt stehen – auch die übliche Kurzform „Az."/„Gz." wurde neben
  der ausgeschriebenen Beschriftung nicht erkannt.
- Eine Kreditkartennummer, die mitten in ihrer Vierergruppierung von einem
  Zeilenumbruch getrennt wurde – etwa in einer schmalen Tabellenspalte –,
  blieb bislang vollständig ungeschützt stehen.
- Eine steuerliche Identifikationsnummer, die mitten in ihrer Gruppierung
  von einem Zeilenumbruch getrennt wurde – etwa in einer schmalen
  Tabellenspalte oder einem Formularfeld –, blieb bislang vollständig
  ungeschützt stehen.
- Eine Sozialversicherungsnummer, die mitten in ihrer Gruppierung von einem
  Zeilenumbruch getrennt wurde – etwa in einer schmalen Tabellenspalte –,
  blieb bislang vollständig ungeschützt stehen, nicht einmal teilweise
  ersetzt.
- Eine Hausnummer mit Bereich wie „12a-14b" oder „3-5" wurde nur zur Hälfte
  ersetzt – der zweite Teil hinter dem Bindestrich blieb offen im Ergebnis
  stehen.
- Eine Fahrgestellnummer (FIN/VIN), die mitten in ihren 17 Zeichen von
  einem Zeilenumbruch, Leerzeichen oder Bindestrich getrennt wurde – etwa in
  einer schmalen Tabellenspalte oder einem Fahrzeugschein-Feld –, blieb
  bislang vollständig ungeschützt stehen.
- Eine Brief-/Mailanrede wie „Liebe Anna!" oder „Lieber Hans" – ohne
  Komma nach dem Namen, die häufigste Form in lockeren Mails – ließ den
  Namen vollständig ungeschützt stehen, auch im vollen Dokument mit
  Fließtext und Grußformel darunter.
- Dieselbe Lücke traf auch die lockeren Chat-/Mail-Anreden „Hallo Anna!",
  „Hi Anna!", „Hey Anna!" und „Servus Anna!" ohne Komma – der Name blieb
  ebenfalls vollständig ungeschützt stehen.
- Ein reiner Signaturblock, der direkt mit „MfG" oder „Herzlichst" beginnt
  – etwa aus der Zwischenablage kopiert, ohne vorangehenden Satz – ließ
  den Namen darunter vollständig ungeschützt stehen.
- Ein Feld mit mehreren Personen, etwa „Angehörige: Kaczmarek, Piotr
  (Sohn), Kaczmarek, Anna (Ehefrau)", verschmolz beide Namen samt
  Klammerangabe zu einem einzigen, viel zu langen Treffer – der zweite
  Name blieb dabei teils ungeschützt im Ergebnis stehen.
- Eine Straße ohne „-straße"/„-weg"-Nachsilbe – wie sie auf dem Land
  üblich ist, etwa „Am Marktplatz 5" oder „Im Grund 12" – blieb
  unerkannt, wenn ihr eine Postleitzahl-Ort-Zeile folgte, etwa in einer
  Meldebescheinigung: „Neue Anschrift: Am Weidengarten 17, 54295 Trier"
  verlor die Straße vollständig, nur die Postleitzahl wurde entfernt.
- Ein Name hinter einer zusammengesetzten Feldbeschriftung mit
  Schrägstrich (etwa „Name/Vorname: Bauer Klaus") wurde teilweise nicht
  erkannt – ein mehrdeutiger Nachname wie „Bauer" blieb ohne den
  Feldbeleg unentdeckt. Dieselbe Lücke traf Kombifelder wie
  „PLZ/Ort: 04109 / Leipzig". Dasselbe galt für Kombifelder mit
  ausgeschriebenem Verbinder statt Schrägstrich, etwa
  „Vor- und Nachname: Bauer Klaus" oder „Nachname bzw. Vorname: …".
- Ein Geburtsdatum in der Form „Datum der Geburt: …" und ein Sterbedatum
  in der Form „Todesdatum: …" oder „Datum des Todes: …" wurden nicht
  erkannt – nur „Geburtsdatum: …" bzw. „Sterbedatum: …" griffen.
- Ein Hochzeitsdatum in der Form „Datum der Heirat: …" oder „Datum der
  Hochzeit: …" wurde nicht erkannt – nur „Hochzeitsdatum: …",
  „Heiratsdatum: …" und „Datum der Eheschließung: …" griffen, obwohl
  Scheidungs-, Einbürgerungs- und Verpartnerungsdatum dieselbe
  „Datum der X"-Form längst kannten.
- Ein Scheidungsdatum in der Form „Datum der Scheidung: …" wurde nicht
  erkannt – nur „Scheidungsdatum: …" und die nachgestellte Verbform
  griffen, obwohl Einbürgerungs- und Verpartnerungsdatum dieselbe
  „Datum der X"-Form von Anfang an kannten.
- Ein Verpartnerungsdatum wurde bisher gar nicht erkannt – weder mit
  Beschriftung („Verpartnerungsdatum: …", „Datum der Lebenspartnerschaft:
  …") noch im Fließtext („… wurden am … verpartnert"). Jetzt wird es wie
  Geburts-, Hochzeits-, Scheidungs- und Einbürgerungsdatum als eigene
  Angabenart ersetzt.
- Ein Einbürgerungsdatum wurde bisher gar nicht erkannt – weder mit
  Beschriftung („Einbürgerungsdatum: …") noch im Fließtext („… wurde am …
  eingebürgert"). Jetzt wird es wie Geburts-, Hochzeits- und
  Scheidungsdatum als eigene Angabenart ersetzt.
- Ein Scheidungsdatum wurde bisher gar nicht erkannt – weder mit
  Beschriftung („Scheidungsdatum: …") noch im Fließtext („Die Ehe wurde
  am … geschieden"). Jetzt wird es wie Geburts-, Sterbe- und
  Hochzeitsdatum als eigene Angabenart ersetzt.
- Ein Hochzeitsdatum hinter dem Genealogie-Ehezeichen „⚭" ohne Beschriftung
  wurde nicht erkannt, obwohl Geburts- und Sterbedatum in derselben Zeile
  über Stern und Kreuz schon erkannt wurden – jetzt wird auch das
  Hochzeitsdatum erkannt.
- Ein Sterbedatum hinter dem Traueranzeigen-Kreuz ohne Beschriftung
  („*03.06.1940 †21.11.2023") wurde nicht erkannt, obwohl das Geburtsdatum
  davor über den Genealogie-Stern schon erkannt wurde – jetzt wird auch das
  Sterbedatum erkannt.
- Nachname vor Vorname am Ende einer Betreff-/Ticketzeile mit vorangestelltem
  Sachtext und Trennstrich („Betreff: Reklamation - Bauer, Anna") wurde bei
  einem berufsnamengleichen Nachnamen nicht erkannt – jetzt wird er erkannt.
- Bewerber- und Antragstellernummern hinter ihrer Beschriftung
  („Bewerbernummer: 4471829", „Antragstellernummer: 7654321") fielen
  komplett durch die Erkennung – jetzt werden sie erkannt.
- Ersetzen schwärzt nicht mehr, wenn kein Platz für einen lesbaren
  Platzhalter ist – ein zu kleiner Platzhalter wird jetzt kleiner
  geschrieben statt zu einem leeren Balken zu werden, solange überhaupt
  Platz bleibt. Neu außerdem: Ob eine Fundstelle auf einem Bild (Briefkopf,
  Scan-Hintergrund) beschriftet oder nur geschwärzt wird, lässt sich jetzt
  unabhängig von der übrigen Ergebnisart einstellen. Und eine Fundstelle
  auf einem Bild, das ganz entfernt wird, wurde beschriftet, als bliebe das
  Bild stehen – der Platzhalter stand hell auf einem Grund, der nie
  geschwärzt wurde, und verschwand so unsichtbar auf dem jetzt weißen
  Papier.
- Eine Fundstelle auf einem **behaltenen** Bild wurde beim Ersetzen immer
  schwarz-weiß geschwärzt, unabhängig von der gewählten Darstellung
  (Kategoriefarben, Regenbogen …) – sichtbar als Bruch zwischen bunten
  Etiketten im Fließtext und schwarzen Balken auf dem Briefkopf. Der
  Bildgrund folgt jetzt derselben Farbe wie der Platzhalter daneben.
- Die Erkennung der Fahrzeug-Identifizierungsnummer (FIN/VIN) markierte
  jeden 17-stelligen alphanumerischen Code ohne I/O/Q bedingungslos als
  Fahrgestellnummer – auch Auftrags-, Serien- und Lizenzschlüsselnummern,
  die zufällig dieselbe Form haben. Jetzt zählt sie nur noch mit einem
  Kontextwort in der Nähe („FIN", „VIN", „Fahrgestell", „Chassis" u. Ä.).
- In Ticket-/Kalendersystemen riss die Namenserkennung nach „Assigned to"/
  „Closed by" u. Ä. das nächste Feldwort mit, wenn es in derselben Zeile
  ohne Trenner direkt folgte („Assigned to Max Mustermann Priority High"
  wurde zu „Max Mustermann Priority"). In Git-Commit-Kopfzeilen riss die
  Namenserkennung ebenso den **nächsten** Trailer-Schlüssel mit, wenn zwei
  Zeilen mit nur einem Leerzeichen statt Zeilenumbruch aneinanderhingen
  („Author: julia bergmann Reviewed-by: …" wurde zu „julia bergmann
  Reviewed-by"). Beide Bremsen ergänzt.
- Der Name hinter „p.A.", „zH"/„zHd", „i.A."/„i.V." und „geb." riss ein
  direkt folgendes Abteilungswort in denselben Treffer, wenn es ohne
  Trenner in derselben Zeile stand („p.A. Max Mustermann Buchhaltung"
  wurde zu „Max Mustermann Buchhaltung", „i.A.Max Mustermann Vertrieb" zu
  „Max Mustermann Vertrieb"). Dieselbe Bremse wie bei „Assigned to"/
  Git-Trailern jetzt auch hier ergänzt.
- Eine beschriftete IBAN direkt über der BIC-, BLZ- oder SWIFT-Zeile riss
  deren Beschriftung mit in ihren eigenen Treffer, weil „BIC" und „BLZ"
  selbst wie ein weiterer Nummernblock aussahen – aus „IBAN: DE89 …
  0130 00“ und der Zeile darunter wurde ein einziger, zu weit reichender
  Treffer, und die Beschriftung der nächsten Zeile verschwand beim
  Bereinigen mit. Betroffen war fast jede Bankverbindung mit IBAN und BIC
  untereinander.
- Das Trefferpanel sagt jetzt, **wo** ein Platzhalter steht, den es auf der
  Seite nicht finden kann. Zwei Fälle meldeten bisher nur „nicht gefunden“,
  obwohl die Ersetzung stattfand: Steht der Platzhalter in nicht sichtbarem
  Nebentext – etwa der Verweisadresse eines Links, einer Anmerkung oder
  einem Formularfeld –, trägt die Zeile das jetzt als eigene Auskunft
  („im Nebentext“), und der Klick erklärt es. Und wurde der Platzhalter
  mangels Platz gekürzt geschrieben („[N382]“ statt „[NAM382]“), springt
  der Klick auf die lange Zeile jetzt zur Kurzform-Stelle und nennt die
  Umbenennung; die Zuordnung verzahnt beide Zeilen dafür ausdrücklich
  miteinander.
- Steht derselbe Ersatzwert mehrmals im Dokument, springt jeder weitere
  Klick auf die Panelzeile im Kreis zur nächsten Fundstelle – auch über
  Seitengrenzen; die Statuszeile zählt mit („Fundstelle 2 von 4“), und die
  gerade angesteuerte Stelle ist satter gerahmt als die übrigen. Und wenn
  ein Platzhalter nur in der Trefferliste steht, aber nirgends im Dokument
  (weil die Stelle in einer überlappenden Ersetzung aufging), sagt die
  Statuszeile das jetzt, statt dass der Klick stumm folgenlos bleibt.
- Ein abgekürzter Vorname hinter „an" oder „für" wird jetzt zuverlässig als
  Name erkannt – „Überweisung an M. Wagner" und „Rechnung für M. Wagner"
  blieben bisher oft unbereinigt stehen, während derselbe Name mit anderer
  Beschriftung davor (etwa „Zahlungsempfänger:") schon gefunden wurde.
  Betroffen waren vor allem Kontoauszugs- und Buchungszeilen.
- „Angeklagter"/„Angeklagte"/„Beschuldigter"/„Beschuldigte" gelten jetzt als
  Namensfeld: Stand ein Name in Strafverfahrensschriftstücken direkt hinter
  einer dieser Beschriftungen, wurde er bislang für rund die Hälfte der
  geprüften Namen gar nicht erkannt – weder Vor- noch Nachname.
- Die vom Trefferpanel angeklickte Stelle wird jetzt blau gerahmt statt
  gelb markiert – auf den farbigen Prüfampel-Flächen war das Gelb der
  Suchtreffer nicht zu erkennen. Außerdem findet der Klick jetzt auch
  mehrwortige Ersatzwerte (erfundene Namen, maskierte Nummern): Bisher
  blieb er bei solchen Zeilen wirkungslos, weil die Fundstelle nur Wort
  für Wort gesucht wurde.
- Adoptiv-, Pflege- und Stiefeltern („Adoptivvater", „Pflegemutter",
  „Stiefvater" und Weiteres) werden jetzt als Namensfeld erkannt, der Name
  fiel vorher unbereinigt durch
- Zahlenreiche Tabellen und Listen werden nicht mehr fälschlich verworfen:
  Wurde eine kurze Zahl (etwa ein als Rufnummer verlesener
  Kundennummernteil) ersetzt, meldete die Schlussprüfung dieselbe
  Ziffernfolge auch dann als verbliebene Angabe, wenn sie anderswo nur
  zufällig in einer ganz anderen Nummer steckt – und lieferte dann gar
  kein Ergebnis. Eine Zahl zählt jetzt nur noch als Rest, wo sie als
  eigene Zahl steht.
- Personenstandsurkunden: „Vater:"/„Mutter:" wird jetzt als Namensfeld erkannt, der Elternname fiel vorher unbereinigt durch
- Weitere Familienrollen („Pate", „Großvater/-mutter", „Ehepartner",
  „Lebenspartner", „Onkel", „Tante") werden jetzt als Namensfeld erkannt,
  der Name fiel vorher unbereinigt durch
- Die deutsche Bankleitzahl wird jetzt auch amtlich gruppiert erkannt
  ("370 400 44", "370.400.44", "370-400-44", "370/400/44"), nicht mehr nur
  als acht zusammenhängende Ziffern.
- Die deutsche Rentenversicherungsnummer wird jetzt auch mit Punkt,
  Bindestrich oder Schrägstrich zwischen den fünf Blöcken erkannt
  ("65-170839-J-08-8", "65.170839.J.08.8"), nicht mehr nur mit Leerzeichen.
- Das Hauptfenster erscheint schneller: Die Erkennungsbibliotheken
  (Presidio samt Sprachmodell-Unterbau) wurden bisher schon beim
  Fensteraufbau geladen – auf Windows rund vier Sekunden, bevor überhaupt
  etwas zu sehen war. Sie laden jetzt vollständig im Hintergrund; der
  Knopf „Bereinigen" wird wie bisher erst frei, wenn alles bereitsteht.
- Office-Dokumente mit vielen Bildern oder Videos werden schneller
  geschrieben: Schon komprimierte Medien werden im Ergebnispaket
  gespeichert statt nutzlos ein zweites Mal komprimiert – das sparte
  bislang kein Byte und machte JPEGs eher größer.
- Tabellenkalkulationen und andere Dokumente aus vielen kleinen
  Texteinheiten werden schneller geprüft: Die Spracherkennung verarbeitet
  alle Zellen und Absätze eines Dokuments jetzt in einem Durchlauf statt
  einzeln – bei nachweislich denselben Funden (400 Zellen: von rund
  4,7 auf 2,5–3,5 Sekunden).
- Listenartige PDF-Seiten (Verzeichnisse, Positionslisten) sind beim
  Einsetzen der Platzhalter deutlich schneller: Die Platzsuche je
  Beschriftung lief bisher über alle Wörter der Seite – jetzt nur noch
  über die Zeilenumgebung, bei nachweislich gleichem Ergebnis (auf einer
  Seite mit 300 Beschriftungen rund sechzehnmal schneller).
- Bildreiche Dokumente sparen mehrere unnötige Arbeitsschritte je Bild:
  Das Zählen von Gesichtern und Codes auf PDF-Seiten dekodiert das
  Seitenbild nicht mehr doppelt, das Prüfen auf Metadaten entschlüsselt
  ein sauberes Bild gar nicht mehr erst, verpixelte Bilder werden mit der
  normalen statt der langsamsten PNG-Kompression geschrieben (gleiche
  Größe, ein Drittel der Zeit), und ohne eingestelltes Wasserzeichen
  entfällt das nutzlose Neuschreiben der ganzen PDF am Schluss.
- Gescannte PDFs mit eingeschalteter Texterkennung sind deutlich schneller
  durch: Jede Seite wurde bisher zweimal in voller Auflösung gerendert
  (einmal zum Lesen, einmal zum Rastern) – das Abbild wird jetzt
  wiederverwendet. Und auf Windows/Linux liest die Texterkennung die
  Streifen eines großen Scans in einem Durchgang statt mit einem eigenen
  Programmstart je Streifen.
- Große Dokumente werden deutlich schneller bereinigt: Der Abgleich schon
  gefundener Werte wuchs bisher mit der Zahl der Fundstellen (ein
  64-KB-Textblock kostete am Ende einer großen Datei rund eine Sekunde
  nur dafür, jetzt ein Sechzigstel), und die Suche nach Firmen-Rechtsformen
  lief mit allen ~280 Katalogformen über jede Textstelle (jetzt rund
  zwanzigmal schneller, bei nachweislich denselben Funden).
- Ein Name direkt nach „Beste Grüße"/„Beste Wünsche" ohne vorangehenden
  Text oder Satzzeichen wurde gar nicht erkannt – ein reiner
  Signaturblock ohne Fließtext davor ließ den Namen spurlos
  verschwinden.
- Ein Anschriftenfeld am Dokumentanfang mit einem berufsnamengleichen
  Nachnamen („Bauer Anna", „Koch Stefan" als erste Zeile über Straße und
  Ort) blieb bisher teils unerkannt oder wurde als Ortsangabe statt als
  Person eingestuft – ohne vorangehenden Satz fehlte dem Sprachmodell
  der Satzbau, der „Bauer" sonst als Namen und nicht als Beruf erkennen
  lässt.
- Ein Name hinter der Unterschriftsmarke „gez." mit einem
  berufsnamengleichen Nachnamen vor dem Vornamen („gez. Bauer Anna" am
  Ende eines Bescheids oder Urteils) blieb bisher unvollständig erkannt –
  nur der Vorname wurde gefunden, der Nachname verschwand spurlos.
- Ein Name direkt hinter einer Kundennummer, Vertragsnummer oder
  ähnlichen Kennnummer ohne eigene Zeile („Vertragsnummer 55219 Bauer
  Anna", „Kundennr. 4711 Bauer Anna") wurde bei einem berufsnamengleichen
  Nachnamen bisher unvollständig oder gar nicht erkannt.
- Das Symbol in der macOS-Menüleiste ist jetzt eine Vorlage, die sich wie
  die Nachbarsymbole an Hell- und Dunkelmodus anpasst – mit den beiden
  ausgestanzten Balken bleibt es dabei als Maskuro erkennbar. Läuft der
  Zwischenablage-Wächter, zeigt das ein abgesetzter Punkt an der
  Schildspitze.
- Ein Klick im Trefferpanel führt jetzt auch im anonymisierenden Betrieb
  zur Fundstelle: Seite wechseln, ins Bild rollen, gelb markieren. Bisher
  blieb der Klick dort folgenlos, weil er die Platzhalter noch für
  nummernlos hielt – seit jede Fundstelle ihre eigene Nummer trägt, ist
  die Stelle eindeutig. Nur beim tatsächlich nummernlosen Platzhalter
  erklärt die Statuszeile weiterhin, warum kein Sprungziel bestimmbar ist.
- Das erste Speichern im Nachbessern-Editor (Strg+S oder der
  Disketten-Knopf) fragt jetzt nach dem Ort, wie „Speichern unter …“ –
  vorbelegt mit dem Ordner des Originals und dem Ergebnisnamen. Bisher
  landete die Datei wortlos neben dem Original. Wer den Ablageort vorher
  schon über die Statuszeile gewählt hat, wird nicht noch einmal gefragt;
  jedes weitere Speichern schreibt wie bisher dieselbe Datei fort.
- Meldet die Sicherheitsprüfung vor dem Speichern eine auffällige Stelle,
  führt „Zurück zur Prüfung“ jetzt hin: Die erste Fundstelle rollt ins Bild
  und wird rot gerahmt, die Statuszeile nennt sie. Bisher blieb man mit
  Seitenzahl und Punktkoordinaten allein. Aus dem Hauptfenster heraus öffnet
  sich dafür der Editor an der Stelle. Auch beim Hinweis auf eine
  abweichende Seitenzahl führt der Knopf jetzt hin – zur ersten Seite, die
  es nur in einem der beiden Dokumente gibt.
- Wer die Vorschau auf „Nebeneinander in zwei Spalten“ umschaltet, bekommt
  jetzt von selbst ein Fenster, in das beide Bahnen passen – bisher
  quetschten sie sich in die alte Breite, bis man selbst zog. Verbreitert
  wird höchstens bis zum Bildschirmrand und nie zurückverschmälert; eine
  selbst gezogene Breite bleibt stehen.
- Nach- und Vorname in getrennten Tabellenspalten (z. B. „Nachname | Vorname“
  in einer Anmeldebestätigung oder einem CSV-Export) blieben offen – jede
  Zelle für sich sah für die Erkennung wie ein beliebiges Wort ohne
  Namenszusammenhang aus. Werden jetzt erkannt.
- Name und Vorname auf der Rückseite eines EU-Kartenführerscheins blieben
  offen – sie stehen dort hinter den amtlichen Feldcodes „1.“ und „2.“
  statt hinter einem deutschen Wort, und genau das ließ sie unerkannt.
  Werden jetzt erkannt, wenn die Führerscheinnummer (Feldcode „5.“)
  daneben steht.
- Der Vorname des Fahrzeughalters auf der Zulassungsbescheinigung blieb
  offen – er steht hinter dem amtlichen Feldcode „C.1.2“ statt hinter
  einem deutschen Wort wie „Vorname“, und genau das ließ ihn unerkannt.
  Nachname und Vorname unter den Feldcodes C.1, C.1.1 und C.1.2 werden
  jetzt erkannt.
- Die erste Zeile des maschinenlesbaren Bereichs (MRZ) auf Pass oder
  Personalausweis blieb offen – sie trägt den Namen im Format
  „NACHNAME<<VORNAME“ und rutschte auch mit dem neuen MRZ-Erkenner für
  die Prüfziffernzeile komplett durch. Ein Fund zählt jetzt nur, wenn
  direkt daneben eine prüfzifferngültige zweite MRZ-Zeile steht – die
  Namenszeile selbst hat keine eigene Prüfziffer.
- Die zweite Zeile des maschinenlesbaren Bereichs (MRZ) auf Pass oder
  Personalausweis blieb vollständig unerkannt – sie enthält Passnummer,
  Geburts- und Ablaufdatum im Klartext, traf aber keinen einzigen
  bestehenden Erkenner. Ein eigener Erkenner prüft jetzt die vier
  ICAO-Prüfziffern nach.
- Ein KFZ-Kennzeichen ohne jedes Leerzeichen zur Beschriftung blieb offen –
  „KennzeichenM-AB1234" oder „KFZ-KennzeichenM-AB1234" wurden gar nicht
  erkannt, weil die zugrundeliegende Kennzeichenprüfung vor dem Kennzeichen
  ein Nicht-Wortzeichen voraussetzt. Betraf Fahrzeugangaben, bei denen kein
  Leerzeichen zwischen Feldwort und Kennzeichen steht.
- Eine Rufnummer ohne jedes Leerzeichen zur Beschriftung blieb offen –
  „Handynummer0171/2345678" oder „Tel0171/2345678" wurden gar nicht
  erkannt, weil die zugrundeliegende Rufnummernprüfung vor der Nummer ein
  Leerzeichen oder Satzzeichen voraussetzt. Betraf Kontaktangaben, bei
  denen kein Leerzeichen zwischen Feldwort und Nummer steht.
- Ein Geburtsname hinter der Abkürzung „geb." wurde gar nicht erkannt –
  „Julia Bergmann (geb. Weber)" fand nur „Julia Bergmann", der Punkt in
  „geb." ließ das Sprachmodell den folgenden Namen komplett übergehen.
  Betraf Personenangaben mit Geburtsname in Klammern oder hinter Komma.
- Der Vorname vor einem Spitznamen in Anführungszeichen blieb offen, wenn
  Anrede und Titel zusammen davorstanden – „Herr Dr. Klaus "KP" Peters"
  ergab nur „Peters", „Klaus" blieb lesbar stehen. Betraf Unterschriften
  und Kontaktangaben mit Titel und Spitznamen.
- Ein Name hinter der punktlosen Kurzform „zH"/„zHd" (zu Händen) wurde
  gar nicht erkannt – anders als bei „z.Hd." mit Punkt riss die fehlende
  Satzstruktur den Namen mit weg. Betraf Anschriften ohne Punkt in der
  Abkürzung.
- Ein Name hinter „p.A." (per Adresse) wurde gar nicht erkannt – der Punkt
  in der Abkürzung ließ das Sprachmodell die Namenserkennung komplett
  überspringen. Betraf Rechnungen und Bewerbungen mit Sammeladresse.
- Ein Name hinter punktlos angeklebtem „i.A."/„i.V." (im Auftrag/in
  Vertretung) wurde gar nicht erkannt, etwa „i.A.Robert Lang" ohne
  Leerzeichen – derselbe Satzbau-Fehler wie bei „p.A.". Betraf
  Unterschriftenzeilen und E-Mail-Signaturen von Vertretungsfällen.
- Eine reine Anwesenheitsliste im Aufzählungszeichen ohne jede weitere
  Angabe („- Max Mustermann“, auch mit Punkt am Zeilenende) verlor alle
  Namen an dieselbe Bremse, die eigentlich nur Sachaufzählungen wie
  „- Farbe: Blau“ schützen soll. Solche Listen werden jetzt erkannt.
- Dateien, die sich nicht mehr bereinigen ließen, lassen sich wieder
  bereinigen. Ein Wert, der schon durch Erkennung ersetzt war, konnte in
  einer eigenen, bereits ersetzten Marke wie „[SVNR1]“ wiedergefunden werden
  – die Schlussprobe verwarf dann eine tadellos bereinigte Datei. Zudem
  ein Telefonverweis in einer CSV-Tabelle wird jetzt mitentfernt, und wer
  die Suche auf einzelne Arten einschränkt, bekommt sie jetzt überall im
  Dokument gleich – auch im Alternativtext eines Bildes, einer
  Excel-Kopfzeile, einer Auswahlliste oder einem HTML-Attribut.
- Ein Name hinter der E-Mail-Kopfzeile „To:“ (oder „To“ ohne Doppelpunkt)
  wurde nicht erkannt, weil ein fremdes Sprachmodell die ganze Zeile als
  einen einzigen unauffälligen Treffer las und den Namen darin komplett
  verschluckte – anders als bei „Cc:“, „Bcc:“ oder „From:“ vor demselben
  Namen. Ein Name hinter „To“ wird jetzt zuverlässig gefunden.
- Das Hochzeitsdatum ließ sich in eigenen Regeln nicht als Datum behandeln
  („verschieben“ wurde mit „gibt es nur für Datumsangaben“ abgelehnt),
  fehlte in der Gruppenzuordnung der Fundarten – womit es sich über die
  Marken „Was gesucht wird“ nicht abschalten ließ – und bekam statt eines
  kurzen Kürzels wie beim Sterbedatum den vollen Wortlaut als Platzhalter.
  Nachgezogen für alle sechs Kürzel-/Beschriftungstabellen.
- Ein in der Vorschau bewusst abgewählter Wert konnte trotzdem an anderer
  Stelle geschwärzt werden: Wählte man z. B. eine E-Mail-Adresse ab, blieb
  zwar die Adresse selbst stehen, aber ihr lokaler Teil ohne Domäne wurde
  ersetzt, sobald er sich mit dem abgeleiteten Benutzernamen einer weiter
  ausgewählten Person deckte („anna.musterfrau@beispiel.de“ neben „Anna
  Musterfrau“). Ein abgewählter Wortlaut bleibt jetzt dokumentweit tabu,
  unabhängig davon, aus welcher Fundart er stammt.
- Ein Geburtsdatum blieb unerkannt, wenn ein Familienbuch- oder
  Personenstandsauszug es unter einer gemeinsamen Kopfzeile mit dem
  Geburtsort führte („Geburtsdatum, Geburtsort: 19.11.1982, Steyr“) – das
  zweite Feldwort zwischen „Geburtsdatum“ und dem Datum ließ die
  Erkennung bis dahin ganz durchfallen.
- Eine schon erkannte Rufnummer blieb in ihrer verkürzten Bestätigungsform
  lesbar, wenn sie an anderer Stelle im selben Dokument nur noch mit den
  letzten vier Ziffern genannt wurde („erreichbar unter der Nummer
  ...5678“, „Rückruf unter ...5678“) – dieselbe Bauform wie bei IBAN und
  Kreditkarte.
- Eine schon erkannte Kreditkartennummer blieb in ihrer verkürzten
  Bestätigungsform lesbar, wenn sie an anderer Stelle im selben Dokument
  nur noch mit den letzten vier Ziffern genannt wurde („Ihre Kreditkarte
  endet auf ...0366“) – dieselbe in Zahlungsbestätigungen übliche Bauform
  wie bei der IBAN.
- Eine schon erkannte IBAN blieb in ihrer verkürzten Bestätigungsform
  lesbar, wenn sie an anderer Stelle im selben Dokument nur noch mit den
  letzten vier Ziffern genannt wurde („Die IBAN endet auf ...3201“) – eine
  in Bestätigungs-E-Mails übliche Bauform.
- Ein Sprecher in einem Chat- oder Sitzungsprotokoll blieb unerkannt, wenn
  vor seinem Namen eine Anrede stand („Herr Bauer: …“, „Frau Koch: …“) –
  und traf damit oft auch die nächste Sprecherzeile im selben Protokoll
  mit, weil zu wenige erkannte Zeilen übrig blieben, um das Dokument
  überhaupt als Protokoll zu werten.
- Ein Geburtsdatum blieb unerkannt, wenn das Feldwort „geboren“ HINTER dem
  Datum stand statt davor („Das Kind wurde am 14.01.2026 geboren“) – so
  formuliert etwa eine Elternzeit- oder Mutterschutzbescheinigung das
  Geburtsdatum des Kindes. Bisherige Muster setzten das Feldwort immer vor
  dem Datum voraus.
- Eine Formularbeschriftung mit Reaktions- oder Häkchenzeichen direkt davor
  („Ansprechpartner 😊:“, „Kontaktperson ✓:“) wurde nicht mehr als
  Beschriftung erkannt, und der Name darunter oder dahinter blieb dadurch
  teils nur unvollständig gefunden (z. B. nur der Nachname bei „Mayer
  Roman“).
- Dieselbe Lücke traf auch besonders schützenswerte Angaben nach Art. 9
  DSGVO (Religion, Gesundheit, Gewerkschaft): Ein Reaktionszeichen direkt
  vor dem Trenner oder Zeilenumbruch („Konfession 😊: römisch-katholisch“)
  ließ die Beschriftung ganz durchfallen, und die Angabe blieb komplett
  unerkannt stehen.
- Eine Anschrift mit Bindestrich-Doppelname im Ort (z. B. „79761
  Waldshut-Tiengen“, „78050 Villingen-Schwenningen“) verlor die
  Postleitzahl vollständig, obwohl der Ort selbst erkannt und geschwärzt
  wurde – auf einem Fahrzeugpapier oder Anschreiben blieb so die
  Postleitzahl lesbar stehen.
- Eine Tabellenspalte ohne Spaltenabstand (echter PDF-Textauszug) konnte
  unter einer Namensspalte auch zwei zufällig nebeneinanderstehende
  Großschreibungen fälschlich als Person schwärzen, etwa zwei Ortsnamen in
  einer Datenzeile; das ist jetzt nur noch der Fall, wenn kein anderer
  Fund an derselben Stelle bereits etwas anderes erkennt.
- Dieselbe Namensspalte schwärzte in derselben Zeilenform auch zwei dem
  Sprachmodell unbekannte Sachwörter (z. B. „Frontend Backend“, „Turbo
  Modul“) fälschlich als Person, weil dort kein anderer Fund die Bremse
  auslöste; jetzt verlangt sie zusätzlich, dass mindestens eines der
  beiden Wörter vom Sprachmodell selbst als Eigenname gelesen wird.
- Die deutsche Rentenversicherungsnummer wurde in ihrer amtlichen vollen
  Gruppierung (z. B. „65 170839 J 08 8" – so, wie sie auf
  Sozialversicherungsausweis und Lohnabrechnung steht) nicht erkannt und
  blieb im Original stehen; erkannt wurden nur die kompakte Schreibweise
  und die nur bis zum Buchstaben gruppierte Form.
- Die steuerliche Identifikationsnummer wurde in ihrer amtlichen Schreibweise
  (Gruppierung 2-3-3-3, z. B. „48 836 075 988" – so, wie sie auf jedem
  echten Steuerbescheid und jeder Mitteilung des Bundeszentralamts für
  Steuern steht) gar nicht erkannt und blieb im Original stehen; nur die
  seltenere Gruppierung 3-3-3-2 war abgedeckt.
- Die nordrhein-westfälische Steuernummer (z. B. „221/5147/0815", mit
  vierstelliger statt dreistelliger zweiter Gruppe) wurde in
  Steuerbescheiden gar nicht erkannt und blieb im Original stehen –
  jedes andere Bundesland war schon abgedeckt.
- Bei Arbeitsverträgen wurde ein Name hinter der Beschriftung
  „Arbeitgeber:" vollständig übersehen, sobald der Nachname zugleich ein
  gewöhnliches Wort ist (z. B. „Bauer Anna") – „Arbeitgeber" steht sowohl
  als Namens- als auch als Firmenbeschriftung in der Liste, und die
  Firmenzuordnung überschrieb die Namenszuordnung.
- In einem Mietvertragskopf mit den Beschriftungen „Vermieter:"/„Mieter:"
  wurde ein Nachname, der zugleich ein gewöhnliches Wort ist (z. B.
  „Bauer"), übersehen – nur der Vorname blieb erkannt. Nummerierte
  Mietparteien („Mieter 1:", „Mieter 2:") waren zusätzlich betroffen, auch
  bei Namen ohne diese Doppeldeutigkeit.
- In einem Gerichtsprotokoll mit den Beschriftungen „Zeuge:"/„Kläger:"/
  „Beklagter:" (auch mit Zählung, „Zeuge 1:", „Zeuge 2:") wurde ein
  Nachname, der zugleich ein gewöhnliches Wort ist (z. B. „Bauer"), ebenso
  übersehen – nur der Vorname blieb erkannt.
- Bei Erbschein, Vollmacht, Mahnverfahren und Kaufvertrag wurde ein
  Nachname, der zugleich ein gewöhnliches Wort ist (z. B. „Bauer"), hinter
  Beschriftungen wie „Erblasser:", „Erbe:", „Vollmachtgeber:",
  „Bevollmächtigte:r", „Antragsgegner:", „Schuldner:", „Gläubiger:",
  „Käufer:", „Verkäufer:", „Vermächtnisnehmer:" oder
  „Testamentsvollstrecker:" übersehen – teils blieb nur der Vorname
  erkannt, teils fiel der ganze Name weg.
- Bei einer Mehrparteien-Liste vor dem Rubrum-Trennzeichen „./." (z. B.
  „Sand, Werner und Huber, Anna ./. Wechsler, Martina") blieb die erste
  Partei unmaskiert – nur die unmittelbar an „./." angrenzende Partei
  wurde erkannt.
- Im Rubrum-Trennzeichen „./." (z. B. „Sand./.Wechsler") wurde der Name
  nach dem Zeichen vollständig übersehen, wenn dort kein Leerzeichen
  stand – nur mit Leerzeichen davor und danach griff die Erkennung.
- Der Nachname „Wahr" wurde vollständig übersehen, wenn er allein stand
  (z. B. „Frau Wahr bearbeitet Ihren Vorgang.") – das Wort steht zufällig
  auch in der Liste gewöhnlicher deutscher Wörter, die sonst Namensfunde
  aus Sätzen wie „Das ist wahr." filtert.
- Nachnamen wie „Los", „Weit", „Rund" oder „Hoch" wurden vollständig
  übersehen, wenn sie allein standen (z. B. „Herr Hoch übernahm die
  Leitung.") – alle vier Wörter stehen zufällig auch in der Liste
  gewöhnlicher deutscher Wörter, die sonst Namensfunde aus Sätzen wie
  „Rund einhundert Gäste kamen zur Feier." filtert.
- Nachnamen wie „Ganz" oder „Recht" wurden vollständig übersehen, wenn sie
  allein standen (z. B. „Herr Ganz unterschrieb den Vertrag.") – beide
  Wörter stehen zufällig auch in der Liste gewöhnlicher deutscher Wörter,
  die sonst Namensfunde aus Sätzen wie „Ganz genau, das stimmt." filtert.
- Ein Formularfeld mit einem Sternchen oder einer hochgestellten
  Fußnotenziffer hinter der Beschriftung (z. B. „Konfession*:
  römisch-katholisch" oder „Religionszugehörigkeit¹: evangelisch") wurde
  nicht erkannt und blieb im Klartext stehen – nur die Form ohne dieses
  Zeichen griff.
- Dasselbe Feld blieb weiterhin im Klartext stehen, wenn gleich zwei
  Fußnotenzeichen hinter der Beschriftung standen (z. B. „Konfession**:
  römisch-katholisch" oder „Gewerkschaft¹²: ver.di").
- Eine Versionsnummer wie „Softwareversion 4.2.1.19" oder „Firmware Build
  2.0.4.11" wird nicht mehr fälschlich als IP-Adresse geschwärzt. Dasselbe
  gilt jetzt für Beleg- und Vorgangsnummern wie „Rechnungsnummer
  10.20.30.40" oder „Bestellnummer 7.8.9.10".
- Zwei IBANs direkt untereinander (z. B. eigene und die eines
  ausländischen Geschäftspartners im Rechnungskopf) wurden nicht mehr
  beide erkannt – die zweite blieb unbemerkt stehen.
- Eine beschriftete IBAN riss manchmal das folgende Wort im Satz mit
  ("Bankverbindung AT61 … wird belastet" wurde bis "wird" hinein
  geschwärzt), sobald das Folgewort kleingeschrieben war – der Klartextrest
  daneben blieb dabei unangetastet stehen.
- Liechtensteiner Anschriften werden jetzt erkannt („FL-9490 Vaduz"), so wie
  bisher schon deutsche, österreichische und Schweizer.
- Reisepass- und Passnummer werden jetzt hinter ihrer Beschriftung erkannt
  und entfernt (z. B. „Reisepassnummer: C01X00T471").
- Aufenthaltstitel- und Meldebescheinigungsnummer werden jetzt hinter ihrer
  Beschriftung erkannt und entfernt.
- Eine Kennnummer hinter ihrer Beschriftung wird jetzt auch erkannt, wenn
  ein Gedankenstrich statt eines Doppelpunkts trennt (z. B. „Kundennummer –
  K903944").
- Eine als „IBAN" oder „Kontonummer" beschriftete Bankverbindung wird jetzt
  auch erkannt, wenn ein Gedankenstrich statt eines Doppelpunkts trennt.
- Ein Name hinter einer Beschriftung wie „Kontaktperson (Vertrieb)" oder
  „Sachbearbeiter/in" wird jetzt auch mit Klammerzusatz oder
  genderneutraler Schrägstrich-Endung erkannt.
- Dieselbe Sternchen-Genderform („Sachbearbeiter*in") wird jetzt ebenfalls
  erkannt.
- Ein Name hinter einer Beschriftung wird jetzt auch erkannt, wenn ein
  Gleichheitszeichen statt eines Doppelpunkts trennt (z. B.
  „Ansprechpartner = Mayer Roman" oder „Kontaktperson=Mayer Roman"), wie in
  Konfigurationsdateien oder CSV-Kopfzeilen üblich. Stehen mehrere solche
  Beschriftung-Wert-Paare durch Semikolon getrennt in einer Zeile, wird nur
  noch der erste Wert erkannt statt der ganzen restlichen Zeile.
- Ein GPS-Koordinatenpaar hinter dem Wort „Koordinaten" wird jetzt zuverlässig
  erkannt (z. B. „Koordinaten: 48.2082, 16.3738") – das Wort trug die falsche
  Beugungsform im internen Katalog.
- Eine Kennnummer hinter ihrer Beschriftung (Kundennummer, Vertragsnummer,
  Aktenzeichen, Personalausweisnummer und rund hundert weitere Feldwörter)
  wurde nicht mehr erkannt, sobald die Beschriftung nicht genau in der
  hinterlegten Groß-/Kleinschreibung dastand – „kundennummer:" in einer
  E-Mail oder „KUNDENNUMMER:" in einem Formularkopf blieben unangetastet
  stehen.

### Neu

- **Realistische Ersatzwerte sind jetzt ein bewusst eingesetztes Beispiel
  statt einer Vorgabe.** Die Ausnahmentabelle im Reiter „Platzhalter" beginnt
  leer. Ein neuer Knopf trägt dort auf Wunsch plausible Falschwerte für Name,
  Ort, Adresse, Organisation, E-Mail, Telefon, Durchwahl und IBAN ein. Er
  lässt Geldbeträge ausdrücklich beim nummerierten Platzhalter; die Strategie
  „erfinden" bleibt für einzelne Arten weiterhin von Hand wählbar.
- **Die KI-Stufe kann die Grafikkarte nutzen.** Unter Windows lässt sich dafür
  ein knapp 17 MB großes Zusatzpaket nachladen; danach rechnet die KI-Stufe
  auf einer geeigneten Grafikkarte deutlich schneller als auf dem Prozessor.
  Wer keine hat oder nichts nachlädt, arbeitet unverändert weiter – nur eben
  langsamer. Auf macOS ist die Beschleunigung ohnehin schon eingebaut.
- **Zwei neue Benachrichtigungen über das Taskleistensymbol**: wenn die
  Vorschau vor dem Ersetzen zur Durchsicht bereitsteht und wenn eine
  Verarbeitung fertig ist. Beide sind vorbelegt an und lassen sich unter
  *Einstellungen → Programm → Benachrichtigungen* einzeln abschalten.

### Geändert

- **Personalausweis- und Führerscheinnummer werden jetzt erkannt**, wenn
  ihre Beschriftung davorsteht („Personalausweisnummer: …",
  „Führerscheinnummer: …") – bisher fielen beide durch jede Erkennung.
- **Maskuro folgt jetzt den Kontrastdesigns von Windows.** Wer unter
  *Einstellungen → Barrierefreiheit → Kontrastdesigns* eines eingeschaltet
  hat, bekam es bisher überall außer hier: Maskuro setzte danach seine
  eigenen Farben. Jetzt bleibt es beim Design des Systems – Fenster,
  Listen, Ablagezone, Protokoll und Statusfarben. Die farbige Prüfampel in
  Vorschau und Nachbessern-Fenster entfällt dort bewusst; was sie sagt,
  steht seither ohnehin als Zeichen und als Wort daneben.
- **Der Prüfbedarf steht nicht mehr nur in der Farbe.** Rot, Orange und
  Grün sind fast gleich hell – wer eine Rot-Grün-Schwäche hat, sah in
  Vorschau und Trefferfach eine Liste ohne Unterschiede, und das ist etwa
  jeder zwölfte Mann. Jede Zeile trägt jetzt zusätzlich ein Zeichen, das
  sich in der Form unterscheidet: ▲ zuerst prüfen, ● prüfen, ○ gut belegt,
  ◆ ohne Bewertung. Der Kurzhinweis nennt es in Worten, und ein
  Bildschirmleser liest es vor.
- **Alt öffnet die Menüs wieder wie gewohnt.** Die Menüzeile hatte keine
  Tastaturkürzel: Wer die Maus nicht benutzt, musste sich durch jedes Menü
  pfeilen. Jetzt trägt jeder Eintrag einen unterstrichenen Buchstaben –
  Alt+D für „Datei", von dort B für „Beenden" –, und zwar in allen
  Sprachen der Oberfläche.
- **Bedienelemente sagen einem Bildschirmleser wieder, wofür sie da sind.**
  Im Nachbessern-Fenster, im Regelfenster, im Protokoll, in den Wortlisten,
  in der Hilfe, im Suchlauf und in fünf weiteren Fenstern wurden Listen,
  Suchfelder, Klapplisten und Regler bisher nur als „Baum" oder
  „Kombinationsfeld" angesagt – ohne wovon. Rund vierzig Stellen tragen
  jetzt einen Namen. (Das Hauptfenster war seit August in Ordnung; die
  Fenster, die danach dazukamen, hatten den Schritt nie mitgemacht.)
- **Wer mit der Tastatur bedient, sieht überall, wo er steht.** An den
  Prüfbedarf-Reglern, am Kontrollkästchen und am „nie wieder"-Knopf der
  Vorschau, an den Art-Überschriften darin, am Seitenfach des
  Nachbessern-Fensters und an der Seitenleiste der Einstellungen fehlte der
  Rahmen, den das System sonst um das angesprungene Bedienelement legt.
- **Größere Systemschrift schneidet nichts mehr ab.** Wer unter
  *Barrierefreiheit → Textgröße* über 175 % stellt, verlor bisher das Ende
  der Beschriftungen in der Ordnerüberwachung und in den Tastenkürzel-
  Feldern. Die Kapitelliste der Hilfe schnitt lange Kapitelnamen schon bei
  gewöhnlicher Schrift ab; sie bricht sie jetzt um und nennt den vollen
  Namen im Kurzhinweis.

- **Die Erkennung ist deutlich schneller geworden.** Der Erkenner für
  beschriftete Kennnummern („Kundennummer: K903944") prüfte bisher je
  Textabschnitt über 1200 Einzelmuster nacheinander – das war der größte
  Einzelposten der Erkennungszeit, bei jedem Absatz und jeder Tabellenzelle.
  Jetzt ist es ein einziges Muster mit demselben Ergebnis: Am Messkorpus
  ändert sich kein einziger Treffer, die Grundstufe je Textabschnitt wird
  etwa drei- bis viermal so schnell.
- **Das Fenster erscheint beim Start sofort.** Bisher lud das Hauptfenster
  die vollständigen Sprachwerkzeuge, bevor es sich überhaupt zeigte – rund
  vier Sekunden Blindzeit bei jedem Start. Die Modelle laden jetzt wie
  vorgesehen im Hintergrund, während das Fenster schon steht; der
  Bereinigen-Knopf wird wie bisher erst frei, wenn alles bereit ist. Auch
  reine Auskunftsaufrufe der Kommandozeile (etwa `--version`) antworten
  jetzt sofort statt nach mehreren Sekunden.
- **Bilder werden bei automatischer Spracherkennung nur noch einmal
  gelesen.** Bisher lief die Texterkennung bei der Voreinstellung
  „Sprache: automatisch" zweimal über dasselbe Bild - einmal für die
  Sprachvermutung, einmal für die eigentliche Prüfung. Bilddateien,
  Zwischenablage-Bilder und das Textfenster sind damit etwa doppelt so
  schnell fertig; bei abgeschalteter Texterkennung entfällt die bisher
  unbemerkt trotzdem laufende Lesung ganz.
- **Gespeicherte Webseiten und E-Mails werden schneller bereinigt.** Die
  Werte in HTML-Attributen, Kommentaren und eingebetteten Datenblöcken
  wurden bisher einzeln erkannt – eine Gemeindeseite mit hunderten
  Beschriftungen stellte hunderte Einzelfragen an die Erkennung. Jetzt
  werden sie gesammelt und je unterschiedlichem Wert nur einmal erkannt;
  am Messkorpus ändert sich kein Treffer, .html und .eml sind rund ein
  Drittel schneller.
- **Auch die Nebenablagen von Tabellen und Präsentationen werden gebündelt
  erkannt.** Alternativtexte, Formel-Zeichenketten, Diagrammbeschriftungen,
  Kommentare, Pivot-Zwischenspeicher und Dokumenteigenschaften stellten je
  Wert eine eigene Erkennungsfrage – eine Mappe mit tausenden Pivot-Zeilen
  entsprechend tausende. Jetzt läuft ein gesammelter Lauf über die
  unterschiedlichen Werte, und der Nachzieh-Volldurchgang am Ende läuft nur
  noch, wenn seit dem Fließtext tatsächlich neue Werte dazugekommen sind.
  Am Messkorpus ändert sich kein Treffer.
- **Formularreiche PDFs werden schneller bereinigt.** Felder, Notizen,
  Lesezeichen und Verweise wiederholen dieselben Werte massenhaft
  („Off" an jedem Ankreuzfeld, derselbe Verfasser an jeder Anmerkung) –
  jeder stellte bisher seine eigene Erkennungsfrage. Je Lauf wird ein
  Wert jetzt nur noch einmal erkannt; Ersetzung und Konsistenz-Nachpass
  laufen unverändert je Stelle.
- **Große Tabellen-Dateien (.csv/.tsv) werden deutlich schneller
  bereinigt.** Die vier Tabellen-Nachpässe zerlegten dieselbe Datei
  bisher jeweils selbst zeichenweise in Zellen (bei 40 MB rund 30 s
  Mehrarbeit); jetzt läuft die Zerlegung einmal. Die Spaltenkopf-Erkennung
  (Geburtsdatums- und Personalnummern-Spalten) stellt statt einer Frage je
  Zelle eine gebündelte – bei identischen Treffern rund zwanzigmal
  schneller. Und die Namensspalten-Zusammenfassung großer Personallisten
  ist nicht mehr quadratisch in der Zeilenzahl.
- **Die Kennzahlen-Klappe friert das Fenster nicht mehr ein.** Das Aufklappen
  der Kennzahlen las bei vielen großen Dateien deren Text erst zusammen und
  ließ das Fenster dabei sekundenlang stehen. Die Berechnung läuft jetzt im
  Hintergrund; die Klappe öffnet sofort und trägt die Zahlen nach.
- **Der Suchlauf-Bericht friert das Fenster nicht mehr ein.** Nach dem
  Durchsuchen vieler tausend Dateien wurde der gemeinsame Ordner für jede
  betroffene Datei neu berechnet; bei großen Läufen stand das Fenster dabei
  zweistellige Sekunden. Der Bericht erscheint jetzt sofort.
- **PDFs mit Texterkennung werden schneller geprüft.** Jede Seite wurde beim
  Gegenlesen unnötig zweimal ins PNG-Format gewandelt; jetzt wird das schon
  vorliegende Bild durchgereicht. Das Ergebnis ist unverändert, nur die Prüfung
  läuft zügiger.
- **Verlaufs-Anmerkungen auf großen Bildern ruckeln nicht mehr.** Beim
  Nachziehen an den Griffen einer Anmerkung mit Verlauf wurde der Verlauf
  bisher Punkt für Punkt neu berechnet – auf einem großen Bildschirmfoto ein
  sichtbares Stocken. Das Ergebnis ist dasselbe, nur ohne die Pause.

### Behoben

- **Das Kreuz zum Entfernen einer Datei aus der Liste ist wieder ein
  schlichtes X.** Das neue Editor-Werkzeug „Entfernen“ hatte versehentlich
  dieselbe Symbolkennung benutzt und dadurch sein rotes Kreuz samt
  gestrichelter Textlinie auch in jeder Dateizeile gezeigt. Beide Handlungen
  besitzen nun getrennte Symbolnamen und behalten ihre jeweils passende
  Darstellung.
- **Mehrteilige Angaben werden in PDFs auch über einen sichtbaren
  Zeilenumbruch hinweg erkannt.** Maskuro liest den geometrisch erzeugten
  Seitentext zusätzlich als offsetgleiche Fließtextansicht. Das gilt für alle
  Grund- und Hochstufen-Erkenner sowie eigene Suchmuster, nicht nur für den
  zuerst sichtbaren Fall „Diabetes mellitus Typ 2“. Leerzeilen und erkannte
  Tabellen- oder Abschnittsgrenzen bleiben harte Grenzen; Fundstellen passen
  weiterhin exakt auf die zu schwärzenden Wörter.
- **Das Beispiel bei „Pseudonymisieren“ widersprach sich selbst.** Der Satz
  versprach „gleiche Person, gleiche Nummer“ und zeigte dann zwei
  verschiedene Nummern – genau das Bild, das bei „Anonymisieren“ richtig
  ist. Beide Beispiele stimmen jetzt mit ihrem eigenen Satz überein.
- **Ein frisch eingesetzter Platzhalter konnte beim „Original zurückholen“
  als überlagerter Buchstabenmatsch stehen bleiben statt zu verschwinden.**
  Ein einfarbig eingelegter Platzhalter schrieb bisher ein eigenes
  Ausgabekommando je Zeichen, von denen nur das erste eine eigene
  Textmatrix trug – beim nächsten Bearbeiten derselben Stelle (etwa
  „zurückholen“ direkt danach) bekamen die übrigen Zeichenkommandos reihum
  die Zeichenindizes des ersten zugewiesen, und der Platzhalter zerfiel in
  zwei sich überlagernde Positionen. Ein einfarbiger Platzhalter bekommt
  jetzt ein einziges Ausgabekommando für seinen ganzen Text.

- **Stand derselbe geschwärzte oder entfernte Wert unter zwei Zeilen im
  Nachbessern-Fenster und wurden beide für die Rücknahme markiert, zählte
  die zweite Zeile fälschlich als „nicht eindeutig“ – obwohl der Wert
  längst zurückgeholt war.** Beide Zeilen gelten jetzt als geschafft.

- **Der Name nach „Reply-To:" wird jetzt gefunden.** In einer E-Mail-Kopfzeile
  wie „Reply-To: Huber" blieb der Name bisher ganz unerkannt – das
  Sprachmodell las „Reply-To:" als eine eigene, falsche Person und übersah
  den echten Namen danach.

- **Die E-Mail-Kopfwörter „Reply" und „Fwd" werden nicht mehr selbst als
  Name geschwärzt.** In einer Betreffzeile wie „Fwd: Angebot von Huber"
  wurde bisher zusätzlich zum Namen auch das Kopfwort selbst als Person
  erkannt und geschwärzt.

- **„Arbeitgeber: Siemens AG" wird jetzt als Firma erkannt, nicht mehr als
  Person.** Trug der Firmenwert hinter der Beschriftung „Arbeitgeber" eine
  Rechtsform wie GmbH, AG oder KG, blieb er trotz zugeschalteter
  Organisationserkennung ein Personenfund – nur der schmalere Fall ohne
  Rechtsform („Wollmuth und Partner") wurde bisher als Firma erkannt.

- **Eine einmal erkannte Anschrift bleibt nicht mehr an anderer Stelle
  stehen.** Wurde eine Straßenanschrift an einer Stelle erkannt und ersetzt,
  konnte dieselbe Anschrift an einer zweiten Stelle liegen bleiben – etwa in
  einer schwer lesbaren Fußzeile eines eingescannten Dokuments, wo die
  automatische Texterkennung sie verstümmelt las. Anschriften werden jetzt,
  wie Namen und Firmen schon länger, im ganzen Dokument durchgängig entfernt.

- **E-Mails mit mehreren Empfängern wurden beim Bereinigen still beschädigt.**
  Eine `.msg`-Nachricht mit zwei oder mehr Empfängern verlor beim Speichern
  Teile ihres inneren Aufbaus, sodass das bereinigte Ergebnis unvollständig
  war. Ursache war eine Verwechslung gleich benannter innerer Bestandteile,
  die bei jedem Empfänger vorkommen. Solche Nachrichten werden nun vollständig
  wieder aufgebaut.

- **Zwei der mitgelieferten Testdokumente ließen sich nicht in Word und
  PowerPoint öffnen.** Wer den Messkorpus herunterlud, bekam bei
  `format_dokument.docx` „Fehler beim Öffnen der Datei in Word“ und bei
  `format_praesentation.pptx` „Die Datei ist beschädigt“. Beide Dateien
  waren schon fehlerhaft, bevor Maskuro sie anfasste – die bereinigte
  Fassung trug den Fehler nur weiter. LibreOffice öffnete beide
  anstandslos, weshalb es niemandem aufgefallen war.

- **Eine eigene KI im Internet wird jetzt verschlüsselt angesprochen.** Wer
  bei der eigenen KI eine auswärtige Adresse ohne „https://“ einträgt (wie sie
  oft auf dem Zettel der IT steht), erreichte sie bisher über eine
  unverschlüsselte Verbindung – der ungeschwärzte Text ging im Klartext hinaus.
  Solche Adressen werden nun über „https://“ angesprochen; ein Server im
  eigenen Netz bleibt unverändert erreichbar. Folgt der Server einer Umleitung
  auf einen anderen Rechner, wandert der Zugangsschlüssel nicht mehr mit.

- **Auch ein beschädigtes Bild verliert jetzt seine versteckten Metadaten.**
  Ließ sich ein eingebettetes Bild nicht mehr vollständig öffnen (etwa ein
  abgeschnittenes Foto), behielt es bisher seine EXIF- und GPS-Daten –
  Aufnahmeort und Fotografenname blieben unsichtbar im Ergebnis. Solche
  Bilder werden nun auch dann von diesen Daten befreit, wenn sie sich gar
  nicht mehr anzeigen lassen.

- **Eine eingebettete Datei, die sich nicht bereinigen ließ, wird jetzt
  gemeldet statt stillschweigend mitgegeben.** Lag in einer Präsentation oder
  Mappe ein eingebettetes Objekt, das zu tief verschachtelt war oder sich
  nicht öffnen ließ, blieb es bisher unverändert im Ergebnis, ohne Hinweis –
  die Datei galt als bereinigt. Solche Fälle stehen nun in der Warnung
  „konnten NICHT geprüft werden", genau wie ein eingebettetes Altformat.

- **Dunkle Listen sind wieder durchgehend dunkel und lesbar.** Auf macOS
  wechselten Dateilisten zwischen fast schwarzen und hellgrauen Zeilen; im
  Nachbessern sah dadurch derselbe grüne, orange oder rote Prüfwert je nach
  Zeile anders aus. Fenster, Listen, Schrift, Platzhalter und Auswahl kommen
  jetzt aus einer gemeinsamen Hell-/Dunkelpalette. Die farbcodierte
  Trefferliste legt außerdem keine Zebrastreifen mehr unter ihre Farben.

- **Berufsangaben mit „als" wurden fälschlich als Name geschwärzt.** Ein Satz
  wie „Als Koch ist er seit vier Jahren bei uns tätig." verlor den Beruf,
  nicht nur einen Namen – „als" leitet eine Rollenangabe genauso ein wie „der"
  oder „die". Echte Nachnamen an derselben Stelle (z. B. mit einer Anrede
  davor) bleiben unberührt.

- **Eine Tabellenüberschrift konnte eine Positionsnummer in einen Geldbetrag
  hineinziehen** (nur bei eingeschalteter Option „Geldbeträge ebenfalls
  entfernen"). Endete eine Zeile auf eine Währung („… Einzelpreis EUR") und
  begann die nächste mit einer Zahl, wurde daraus fälschlich ein Betrag über
  den Zeilenumbruch hinweg. Das Trennzeichen zwischen Währung und Zahl bleibt
  jetzt auf derselben Zeile.

- **Eine kurze Abkürzung in Großbuchstaben konnte einen ganzen Satzteil
  verschlucken, oder sich vor einen richtig erkannten Namen hängen.** Stand
  in einer Zeile ein zweibuchstabiges Großwort wie „DI", „AG" oder „KG" –
  alltägliche Abkürzungen, keine Namen –, wurde die ganze Zeile probeweise
  kleingeschrieben durchsucht, und die Abkürzung zog dabei gelegentlich
  benachbarte Wörter (auch Verben) in einen einzigen vermeintlichen Namen
  hinein. Erst ab drei Buchstaben löst ein großgeschriebenes Wort diese
  zweite Prüfung jetzt aus. Bei etwas längeren Kürzeln wie „CEO" oder „USB"
  blieb ein zweiter Fehler: Der schon richtig gefundene Name („Schneider")
  bekam das vorangestellte Kürzel als Vorsilbe mit ins Ergebnis gezogen
  („CEO Schneider“). Das Kürzel bleibt jetzt außen vor.

- **Ein Geburtsdatum ohne Leerzeichen dahinter blieb stehen.** Stand hinter
  „geb." keine Lücke vor dem Datum – wie in eng gesetzten Formularen üblich
  („geb.14.03.1988") –, erkannte Maskuro das Feld nicht und ließ das Datum
  unangetastet. Verbreitete Kurzformen wie „Geburtsdat." oder „Geb.-Dat."
  werden jetzt ebenfalls erkannt.

- **Eine IBAN mit Schrägstrichen als Trennzeichen blieb stehen.** Wie bei
  Telefonnummern („0664/1234567") schreiben manche Vorlagen auch die IBAN
  in Blöcken mit Schrägstrich („AT48/3200/0000/1234/5864") statt mit
  Leerzeichen oder Bindestrich. Diese Schreibweise wird jetzt ebenfalls
  erkannt.

- **Eine österreichische Sozialversicherungsnummer mit Bindestrich, Punkt
  oder Schrägstrich blieb stehen oder war falsch beschriftet.** Zwischen
  den beiden Zahlenblöcken war bisher nur ein Leerzeichen vorgesehen;
  Schreibweisen wie „1237-010180", „1237.010180" oder „1237/010180"
  wurden nicht (oder im Schrägstrich-Fall unter der falschen Art) erkannt.
  Die Prüfziffer bestätigt weiterhin jeden Treffer, unabhängig vom
  Trennzeichen.

- **Ein Name hinter „c/o" in einer Anschrift wurde gar nicht erst
  entfernt.** „c/o Max Mustermann, Hauptstraße 5, 1010 Wien" schwärzte
  Straße und Ort, ließ den Namen dahinter aber vollständig stehen. Der
  Name wird jetzt erkannt; „c/o" selbst bleibt als Anschriftenhinweis
  sichtbar.

- **Eine mit Punkten gruppierte Kreditkartennummer blieb stehen.**
  Schreibweisen wie „4111.1111.1111.1111" wurden nicht erkannt; mit
  Leerzeichen oder Bindestrich getrennte Nummern waren davon nicht
  betroffen. Die Prüfsumme bestätigt weiterhin jeden Treffer.

- **Eine mit Bindestrichen gruppierte Steuer-Identifikationsnummer blieb
  stehen, eine österreichische UID mit Bindestrich oder Punkt ebenso.**
  Leerzeichen, Schrägstrich und Punkt waren bei der Steuer-ID bereits
  vorgesehen, der Bindestrich fehlte; bei der UID („ATU12345678") fehlten
  Bindestrich und Punkt nach dem Präfix. Die Prüfziffer der Steuer-ID
  bestätigt weiterhin jeden Treffer.

- **Ein Feldwert in Anführungszeichen blieb stehen, etwa in einer
  JSON-artigen Zeile wie „vorname": „Max".** Die Erkennung über eine
  Feldbeschriftung („Vorname: …") setzte bisher voraus, dass weder die
  Beschriftung noch der Wert selbst in Anführungszeichen stehen. Solche
  Zeilen werden jetzt ebenfalls erkannt – ebenso Feldbeschriftungen mit
  einem vorangestellten YAML-Listenpunkt („- Vorname: Max") oder einem
  Tabulator statt eines Leerzeichens vor dem Doppelpunkt.

- **Das E-Mail-Kopfwort „Sent" wurde selbst wie ein Name geschwärzt.**
  In einer Kopfzeile wie „Sent: Huber" traf es bisher sowohl „Sent" als
  auch den eigentlichen Namen; verwandte Kopfwörter wie „Subject" oder
  „Betreff" blieben davon schon immer unberührt. „Sent" bleibt jetzt
  ebenfalls stehen.

- Ein Name hinter den Kopfzeilen „Errors-To:" oder „Resent-From:" blieb
  unentdeckt, wenn eine solche Zeile in Klartext kopiert stand (etwa eine
  weitergeleitete Nachricht oder ein Vorfallbericht) – anders als bei
  „Reply-To:" oder „Return-Path:" fiel der Name hier ganz weg statt nur
  ungenau abgegrenzt zu sein. Er wird jetzt gefunden.
- Ein und dieselbe Datei ergab bei zwei Bereinigungen manchmal ein
  unterschiedliches Ergebnis: Trafen zwei Erkennungen genau dieselbe Stelle
  mit gleicher Länge und gleicher Sicherheit (z. B. „Sozialversicherungs-
  nummer 1237/010180" als AT_SVNR oder als allgemeine Kennnummer), war es
  vom Zufall abhängig, welche gewann – der Wert wurde in beiden Fällen
  entfernt, nur die Platzhalterbeschriftung wechselte. Der Gleichstand wird
  jetzt immer gleich aufgelöst.
- Eine Funktionsbezeichnung direkt vor einem Hauptwort (z. B. „Behandelnder
  Arzt: Dr. …" oder „Zuständiger Sachbearbeiter ist …") wurde manchmal
  fälschlich mitgeschwärzt, als wäre sie selbst ein Name. Echte Nachnamen
  daneben bleiben davon unberührt.
- Ein echter Nachname, der zufällig gleich aussieht wie ein Eigenschaftswort
  (z. B. „Schöne", „Lange", „Junge") und unmittelbar vor einem weiteren
  Hauptwort steht (etwa „Kontaktperson: Schöne Assistentin"), blieb seit der
  letzten Behebung ungeschwärzt im Text stehen – ein Datenleck. Nur noch eine
  eng begrenzte Liste echter Funktionsbezeichnungen (z. B. „Behandelnder",
  „Zuständiger") wird jetzt in dieser Bauform als Nicht-Name behandelt.
- Ein alleinstehender Nachname am Ende eines mehrzeiligen Namenstreffers,
  der zufällig gleich aussieht wie ein Eigenschaftswort (z. B. „Schwarz",
  „Kurz", „Alt", „Frisch", „Gut", „Reich"), blieb vor einem unmittelbar
  folgenden Doppelpunkt unerkannt stehen – die Bereinigung verwechselte ihn
  mit einer Feldbeschriftung wie „Telefon:". Eine geschlossene Liste
  bekannter mehrdeutiger Nachnamen schützt ihn jetzt.
- Ein alleinstehender Nachname, der zufällig ein gewöhnliches deutsches
  Wort ist („Gross"/„Grosse", „Gut", „Kurz", „Lang"/„Lange"), ging
  bislang **vollständig** verloren – auch in einfachen Sätzen wie „Herr
  Gross unterschrieb den Vertrag." Der Grund lag in der spaCy-eigenen
  Stoppwortliste, die diese Wörter enthält; eine geschlossene Liste
  bekannter Nachnamen bewahrt sie jetzt vor dem Verwerfen.
- Bei Arbeits-, Darlehens-, Bürgschafts-, Treuhand- und Insolvenzverträgen
  sowie Vormundschaft/Pflegschaft und Gutachtenaufträgen wurde ein
  Nachname, der zugleich ein gewöhnliches Wort ist (z. B. „Bauer"), hinter
  Beschriftungen wie „Auftraggeber:", „Auftragnehmer:", „Arbeitnehmer:",
  „Versicherter:", „Darlehensgeber:", „Darlehensnehmer:", „Bürge:",
  „Sicherungsgeber:", „Treuhänder:", „Treugeber:", „Insolvenzverwalter:",
  „Gutachter:", „Sachverständiger:", „Vormund:" oder „Pfleger:" übersehen
  – teils blieb nur der Vorname erkannt, teils fiel der ganze Name weg.
- Im Impressum wurde ein Nachname, der zugleich ein gewöhnliches Wort ist
  (z. B. „Bauer"), hinter den Beschriftungen „Geschäftsführer:",
  „Geschäftsführerin:", „Vertretungsberechtigt:", „Inhaber:" oder
  „Inhaberin:" übersehen – bei „Geschäftsführer:"/„Inhaber:" fiel der ganze
  Name weg, bei „Vertretungsberechtigt:" blieb nur der Vorname erkannt.
- Ein Kontaktblock, dessen Beschriftung allein in ihrer Zeile stand und die
  geschlechtsneutrale Doppelpunktform trug („Ansprechpartner:in", Name
  darunter), wurde **vollständig** übersehen – der Doppelpunkt wurde als
  Feldtrenner gelesen, „in" als (verworfener) Feldwert, und der eigentliche
  Name in der nächsten Zeile kam dadurch nie mehr zum Zug. Die Sternchenform
  („Ansprechpartner*in") war davon nicht betroffen.
- Stand Name und Beschriftung mit derselben Doppelpunkt-Genderform in
  **einer** Zeile („Ansprechpartner:in Anna Berger"), riss der Platzhalter
  das Wort „in" mit in die Ersetzung hinein, statt nur den Namen zu
  entfernen – der Name selbst wurde weiterhin vollständig erfasst.
- Ein Name in einer Tabellenspalte unter einem Personen-Spaltenkopf (z. B.
  „Name Vorname Geburtsdatum" über „Bauer Anna 03.05.1985", wie in einer
  Gehaltsabrechnung) wurde vollständig übersehen, sobald zwischen den
  Spalten nur ein einziges Leerzeichen stand und keine Zeile mit einer
  Gliederungsnummer begann – genau die Gestalt, in der ein echter
  PDF-Textauszug solche Zeilen abliefert.
- In einem Chat- oder Sitzungsprotokoll mit Sprechernamen vor dem
  Doppelpunkt (z. B. „Bauer 🙂: Ich stimme dem Vorschlag zu.") blieb der
  Name vollständig unerkannt, sobald ein Reaktionszeichen zwischen Name
  und Doppelpunkt stand und der Nachname zugleich ein gewöhnliches Wort
  ist („Bauer", „Koch", „Schneider" u. ä.) – ein komplettes Protokoll
  konnte so ohne einen einzigen erkannten Sprecher bleiben.
- Dieselbe Sprecherzeilen-Lücke bestand auch mit anderen Zwischenzeichen
  vor dem Doppelpunkt: einem Statuszusatz in Klammern („Bauer (Vorsitz):
  …", „Bauer (abwesend): …"), einer Uhrzeit in eckigen Klammern
  („Bauer [14:32]: …") und einem Fußnotenzeichen unmittelbar am Namen
  („Bauer*: …"). Auch hier blieb der Sprecher vollständig unerkannt,
  sobald der Nachname zugleich ein gewöhnliches Wort ist.
- Stand eine bereits erkannte Person in einem angehängten Protokoll- oder
  Log-Ausschnitt derselben Nachricht (etwa ein Support-Ticket) zusätzlich
  als Benutzername in der Form „vorname.nachname" – klein geschrieben,
  ohne Leerzeichen, durch einen Punkt verbunden –, blieb dieser
  Klarname lesbar stehen, obwohl derselbe Name im Anschreiben bereits
  geschwärzt war.
- Dieselbe Benutzernamen-Lücke bestand auch mit einem Unterstrich statt
  einem Punkt („vorname_nachname") – ein ebenso verbreitetes Format in
  Protokoll- und Log-Ausschnitten.
- Und auch in umgekehrter Reihenfolge blieb der Benutzername lesbar
  („nachname.vorname" bzw. „nachname_vorname") – manche Systeme stellen
  den Nachnamen im Log-Benutzernamen voran statt hintenan.
- Ein Sterbedatum blieb unerkannt, wenn keine sonstige Angabe daneben
  stand („Herr Bauer ist am 12.03.1985 verstorben“) – dafür gab es bisher
  gar keine eigene Erkennung, und das generische Datum greift bei dieser
  Standardschwelle nicht.
- Ein Sterbedatum blieb auch dann unerkannt, wenn der Satz die Verbform
  statt des Partizips verwendete („Frau Meier verstarb am 12.03.1985“,
  „Er starb am 12.03.1985“) – nur „ist … verstorben“/„ist … gestorben“
  griff bisher.
- Ein Hochzeitsdatum blieb unerkannt, gleich in welcher Form es dastand
  („Eheschließung am 12.03.2010“, „Hochzeitsdatum: 12.03.2010“, „Herr und
  Frau Bauer heirateten am 12.03.2010“) – dafür gab es bisher gar keine
  eigene Erkennung, und das generische Datum greift bei dieser
  Standardschwelle nicht.

- **Im Nachbessern-Editor konnte ein zweiter Rahmen über einem gerade erst
  eingesetzten Platzhalter einen roten Zeichenrest stehen lassen**, etwa
  „[G" statt „[BEG1]" – ohne jede Warnung, denn der Rest gehörte nicht mehr
  zur vertraulichen Angabe (die war schon im ersten Zug entfernt), sondern
  nur noch zum eigenen Platzhalter. Grund war die Farbgebung: Ein neu
  eingesetzter Platzhalter wurde zeichenweise in die Datei geschrieben,
  auch bei einfarbiger Vorgabe – ein späterer Rahmen über derselben Stelle
  fand dadurch keinen zusammenhängenden Wortlaut mehr, an dem er sich
  hätte verorten können. Jetzt steht ein einfarbiger Platzhalter als ein
  Stück im Strom, wie es die automatische Bereinigung schon immer tat; nur
  ein echter Verlauf oder Regenbogentext braucht weiterhin einzelne
  Zeichen. Die eingebaute Gegenprobe erkennt einen solchen Rest zusätzlich
  jetzt auch dann, wenn die exakte Zeichenkette des Platzhalters nicht
  mehr vorkommt.
- Eine nummerierte Namensliste mit gestufter Gliederungsnummer
  („1.1 Max Mustermann“, „1.2 Huber Franz“ …) verlor alle Namen an
  dieselbe Bremse, die eigentlich nur echte Gliederungen und
  Positionslisten schützen soll – ohne Spaltenkopf über der Liste gab es
  keinen Zeugen, an dem sich ein Name hätte retten können.
- Ein Name in einer englischsprachigen Anmeldezeile eines Systemprotokolls
  („Accepted password for Max Mustermann from 10.0.0.5 port 51000 ssh2“)
  wurde nicht erkannt – das deutsche Sprachmodell fand ihn nur, wenn davor
  „invalid user“ stand, sonst blieb er stehen. Solche Protokollausschnitte
  werden oft unverändert einem Vorfallbericht beigefügt. Namen hinter „for“
  vor einer IP-Adresse werden jetzt zuverlässig erkannt.
- Der Name des Zahlungspflichtigen in der SEPA-Mandatsreferenz eines
  Kontoauszugs oder Buchungsjournals (z. B. „MREF+Mustermann Klaus+SVWZ+
  Miete August“) blieb offen – kein Leerzeichen, keine Satzstruktur, nur
  mit „+“ getrennte Großbuchstaben-Felder, und in der dort üblichen
  Reihenfolge „Nachname Vorname“ fand die Erkennung ihn auch nicht
  zufällig. Wird jetzt erkannt.
- Die Straße samt Hausnummer in der ersten Zeile einer Anschriftstabelle
  (z. B. „Nachname | Vorname | Straße | PLZ | Ort“) blieb offen – das
  Sprachmodell riet dort einen falschen, aber längeren Ort quer über
  mehrere Spalten hinweg, und der verdrängte den richtigen, kürzeren
  Anschriftentreffer. Wird jetzt erkannt.
- Dasselbe Leck trat mit einem Tabulator statt „|“ oder „;“ als
  Spaltentrenner auf – dort verschwand die Anschrift sogar ganz statt
  nur zu verlieren. Wird jetzt erkannt.
- Eine Straße mit Hausnummer blieb offen, wenn direkt danach ohne
  Leerzeichen eine Postleitzahl mit Komma folgte (z. B. „Bahnhofstrasse
  12,80331 München“, wie in einer kommagetrennten Tabellenspalte) – das
  Komma sah wie eine Nachkommastelle einer Menge aus, und die Straße galt
  dem Muster deshalb gar nicht erst als Anschrift. Wird jetzt erkannt.
- Eine Straße mit Hausnummer blieb offen, wenn direkt danach ohne Komma
  die Ortsvorsilbe „St.“ (Sankt) folgte (z. B. „Hauptstraße 5 St.
  Pölten“, ein Briefkopf ohne vorangestellte Postleitzahl) – „St.“ sah
  wie die Stückzahl-Einheit aus, und die Straße galt dem Muster deshalb
  gar nicht erst als Anschrift. Wird jetzt erkannt.
- Ein Tür-/Stiegenzusatz nach einer Hausnummer (z. B. „Lerchenfelder
  Gürtel 43/12“) blieb offen sichtbar, wenn direkt danach ein einzelner
  Buchstabe stand, der zufällig mit einer Maßeinheit übereinstimmt (z. B.
  „h“ für Stunde) – die Anschrift wurde dann nur bis zur Hausnummer ohne
  ihren Zusatz bereinigt, statt vollständig oder gar nicht zu greifen.
- Eine Betreffzeile mit einem berufsnamengleichen Nachnamen vor dem
  Vornamen („Betreff: Bauer Anna“, „Betreff: Bauer, Anna“) blieb bisher
  vollständig unerkannt – auch mitten im Dokument mit vorangehendem
  vollständigem Satz. Wird jetzt erkannt.
- Eine deutsche Steuernummer mit Leerzeichen, Punkt oder Bindestrich
  zwischen den Blöcken (z. B. „Steuernummer: 30 815 08153“ oder
  „30.815.08153“) blieb bisher unerkannt – nur die Schreibweise mit
  Schrägstrich wurde gefunden. Wird jetzt erkannt.
- Ein Name hinter einer medizinischen Feldbeschriftung („Patient:“,
  „Hausarzt:“, „Behandelnder Arzt:“, „Überweisender Arzt:“ und ihre
  weiblichen Formen) blieb bisher unerkannt, wenn der Nachname zugleich
  ein gewöhnliches deutsches Wort ist (z. B. „Patient: Bauer Thomas“).
  Wird jetzt erkannt.
- Ein Name hinter der Feldbeschriftung „Zahnarzt“ auf eigener Zeile (z. B.
  „Zahnarzt“, darunter „Huber Franz“) blieb bisher unerkannt – weder Vor-
  noch Nachname. „Zahnärztin“ und die einfache „Arzt“-Form waren davon
  nicht betroffen. Wird jetzt erkannt.
- Ein Nachname hinter „Herr“/„Frau“, auf den eine Amtsdeutsch-Floskel wie
  „zur Kenntnisnahme“, „zur Unterschrift“ oder „zur Weiterleitung“ folgte,
  wurde bisher zu weit gefasst und riss die Floskel mit in den Namenstreffer
  hinein – aus „Frau Petra Klein zur Vertretung in allen Angelegenheiten“
  wurde „Petra Klein zur Vertretung“ ersetzt, und der Rest des Satzes blieb
  grammatisch verstümmelt stehen. Echte Adelsprädikate wie „von der Leyen“
  oder „zu Guttenberg“ bleiben davon unberührt.
- Dieselbe Amtsdeutsch-Floskel-Überredaktion steckte auch hinter dem Namen
  in einer E-Mail-„To:“-Kopfzeile, einem Zulassungscode (C.1/C.1.1/C.1.2),
  einem Führerscheincode, einem geklammerten Formularfeld
  („[Vorname]: …“) und einer unpunktierten Grußformel – überall dort riss
  „zur“/„von“ & Co. eine nachfolgende Floskel wie „zur Unterschrift“ oder
  „zur Vertretung“ mit in den Treffer, teils blieb sogar das bloße
  Partikelwort selbst als Namensrest im Ergebnis hängen. Auch hier bleiben
  echte Adelsprädikate vollständig erhalten.
- Die Matrikelnummer hinter ihrer Beschriftung wurde bisher gar nicht
  erkannt – „Matrikelnummer 7654321“ fiel komplett durch die Erkennung,
  weder als Kennnummer noch über das Sprachmodell, weil die Zahl allein
  keine erkennbare Form trägt.
- Dasselbe galt für die Teilnehmernummer – „Teilnehmernummer 4471829“ fiel
  komplett durch, weder als Kennnummer noch über das Sprachmodell.
- Im Lebenslauf fiel der Name unter der Abschnittsüberschrift „Persönliche
  Daten“ oft ganz oder teilweise durch die Erkennung, wenn er ohne Anrede
  in der Form „Nachname Vorname“ direkt darunterstand.
- Dasselbe galt für die Abschnittsüberschrift „Kontaktdaten“ – dort fiel
  der Name sogar vollständig durch, nicht nur teilweise.
- In einer Meldebescheinigung oder Antragsliste mit zusammengefasster
  Spalte „Name, Vorname“ (Meldewesen-Schreibweise, Wert z. B.
  „Mustermann, Max“ in einer Zelle) fiel der Name komplett durch die
  Erkennung, wenn eine weitere Spalte wie das Geburtsdatum folgte.
- Ein Geburtsdatum in der auf Personalausweis und Meldebescheinigung
  üblichen Form „Geburtsdatum/-ort: 22.07.1978 / Rostock“ wurde nicht
  erkannt – nur die Kommaform „Geburtsdatum, Geburtsort: …“ griff.
- „Bürgerservice“ und „Bürgerbüro“ wurden gelegentlich fälschlich als Ort
  geschwärzt, besonders nach einem Gedankenstrich als Aufzählungstrenner
  (etwa „Wenden Sie sich an das Bürgerservice – Bürgerbüro …“).
- Eine beschriftete Rufnummer, die ein Zeilenumbruch mitten durchtrennte
  (etwa aus einer schmalen Briefkopf-Spalte oder einer PDF-Textextraktion
  an der Spaltenbreite: „Telefon: 0176 12\n34567“), wurde teils nur zur
  Hälfte geschwärzt – der Rest hinter dem Zeilenumbruch blieb lesbar
  stehen.
- Eine beschriftete Kennnummer (Kunden-, Mitglieds-, Vertragsnummer und
  ähnliche), die ein Zeilenumbruch mitten durchtrennte (etwa „Kundennummer:
  K903\n944“ aus einer schmalen Spalte), wurde nur zur Hälfte geschwärzt –
  der Rest hinter dem Zeilenumbruch blieb lesbar stehen.
- Ein Name mit akademischem Titel vor einer Berufsbezeichnung nach Komma
  (etwa „Dipl.-Ing. Sabine Roth, Projektleiterin“) blieb vollständig
  ungeschützt stehen – die Zeile sah wie ein tabellarischer Spaltenkopf
  aus und wurde fälschlich als Sachinhalt verworfen.
- Der Titel „Dr.-Ing.“ (ein häufiger deutscher Ingenieurgrad) vor einem
  Namen wurde nicht in den maskierten Personenwert einbezogen und blieb
  lesbar stehen – derselbe Bindestrich-Fallstrick wie bei „Dipl.-Ing.“.
- Die Titel „Dipl.-Kfm.“, „Dipl.-Kffr.“ und „Dipl.-Psych.“ (Diplom-
  Kaufmann/-Kauffrau/-Psychologe) vor einem Namen wurden nicht in den
  maskierten Personenwert einbezogen und blieben lesbar stehen – derselbe
  Bindestrich-Fallstrick wie bei „Dipl.-Ing.“ und „Dr.-Ing.“.
- Eine MAC-Adresse in der Cisco-Schreibweise mit Punkten statt Doppelpunkten
  (z. B. „aabb.ccdd.eeff“, wie sie Switch-Protokolle und Support-Tickets
  ausgeben) wurde gar nicht erkannt und blieb lesbar stehen.
- Ein Nachname hinter „Familie“ (z. B. „Die Familie Gruber unterschreibt
  den Vertrag“) blieb je nach Satzbau unerkannt und damit lesbar stehen –
  auch mit Adelsprädikat davor („Familie von der Leyen“).

- Bei einer kroatischen Anschrift ohne trennendes Satzzeichen zwischen
  Postleitzahl+Ort und Straße+Hausnummer (z. B. „10000 Zagreb Ulica Ivana
  Lučića 5“) blieb die Hausnummer unbereinigt stehen.

- Bei einer litauischen Kontaktangabe mit der Beschriftung „Kontaktinis
  asmuo“ (z. B. „Kontaktinis asmuo: Vilkas Jonas“) blieb der Nachname
  unerkannt, wenn er zugleich ein gebräuchliches Substantiv war (Vilkas =
  „Wolf“, Vanagas = „Habicht“).

- Ein Geburts- oder Wohnsitzland ohne weitere Beschriftung in einem
  dänischen Formularfeld (z. B. „Fødeland: Tyskland“ oder „Bopæl:
  Tyskland“) wurde nicht erkannt.

- Ein Geburts- oder Wohnsitzland ohne weitere Beschriftung in einem
  rumänischen Formularfeld (z. B. „Țara: Germania“ oder „Țara de
  reședință: Franța“) wurde nicht erkannt.

- Ein Firmenname unter der litauischen Feldbeschriftung „Darbdavys:“
  oder „Įmonės pavadinimas:“ (Arbeitgeber/Firma) wurde nicht erkannt.

- Ein Firmenname unter der russischen Feldbeschriftung
  „Работодатель:“ oder „Наименование организации:“
  (Arbeitgeber/Firma) wurde nicht erkannt.

- Ein ausgeschriebenes Datum mit Monatsnamen auf Rumänisch (z. B.
  „31 decembrie 2024“) wurde nicht erkannt.

- Ein ungarischer Geburtsname hinter der Abkürzung „szül.“ (z. B. „Nagy
  Éva (szül. Kovács)“) wurde nicht erkannt und blieb offen lesbar stehen.

- Eine gespeicherte HTML-Profilseite (oder eine E-Mail mit angehängter
  Webseite) konnte den bürgerlichen Namen unbereinigt lassen, wenn er nur
  in den Open-Graph-Profilfeldern `profile:first_name`/`profile:last_name`/
  `profile:username` stand – diese tragen den Namen zerlegt statt
  beschreibend wie `og:title` und werden jetzt ebenfalls bereinigt.

- Eine Unzustellbarkeitsmeldung (Bounce/NDR) trug oft die Kopfzeilen der
  ursprünglich unzustellbaren Mail (Absender, Empfänger, Betreff) in einem
  eigenen, dritten Anhangsteil – dieser blieb in der bereinigten Fassung
  vollständig unangetastet stehen. Der Teil wird jetzt wie der übrige
  Zustellbericht bereinigt.

- Der individuell benannte Bearbeiter eines geschützten Bereichs in Word (Bearbeitung einschränken → Ausnahmen, `w:permStart`) blieb im Klartext stehen, auch wenn derselbe Name im Fließtext längst bereinigt war. Er wird jetzt ebenfalls entfernt.

## 0.10.42-alpha.20260827 – 27. August 2026

### Neu

- **Benannte Erkennungsprofile machen verschiedene Arbeitsfälle mit einem
  Griff erreichbar.** Unter *Einstellungen → Erkennung → Was entfernt wird*
  lässt sich die aktuelle Kategorien- und Artenauswahl speichern und über ein
  Auswahlfeld sofort wieder anwenden. Das feste Profil *Standard* entspricht
  dem bisherigen Auslieferungsstand und kann nicht gelöscht werden. Ein
  Profil verändert ausschließlich, was entfernt wird; Sprache, Ausgabeart,
  Erkennungstiefe sowie eigene Begriffe und Suchmuster bleiben unberührt.

- **Die Art des Ergebnisses wird jetzt direkt vor dem Bereinigen gewählt.**
  Ein gemeinsames Wahlfeld im Hauptfenster legt für den ganzen Stapel fest,
  ob Maskuro lesbare Platzhalter einsetzt, schwärzt oder ersatzlos entfernt.
  Die zwei getrennten Felder für PDF und Office im Einstellungsfenster sind
  entfallen; dadurch ist die wichtige Entscheidung sichtbar und kann bei
  gemischten Stapeln nicht mehr unbeabsichtigt auseinanderlaufen. Der
  geführte Rundgang erklärt die neue Auswahl vor dem ersten Bereinigen.

- **Themes und Wasserzeichen markieren fertige PDFs auf Wunsch deutlich.**
  Zwölf Gesamtlooks stimmen Ersatztexte und Schwärzungsflächen aufeinander
  ab; neu dabei sind Pride sowie Frühling, Sommer, Herbst und Winter.
  *Geheimakte* bringt direkt ein diagonales `TOP SECRET` mit. Unabhängig
  davon lässt sich ein freier Markierungstext oder ein eigenes Bild, Icon
  beziehungsweise SVG mit Farbe und Deckkraft wählen. Importierte Grafiken
  werden ohne ihre Metadaten eingebettet und bleiben verfügbar, wenn die
  Quelldatei verschoben wird. Beim Nachbessern ersetzt Maskuro sein bisheriges
  Wasserzeichen, statt es mehrfach übereinanderzulegen.
  Textwasserzeichen werden als letzte PDF-Schicht mit heller Kontur gezeichnet,
  damit sie auch auf dunklen Bildern und dichtem Text sichtbar bleiben. Der
  Nachbesserungseditor ignoriert Maskuros Wasserzeichen vollständig und bietet
  dessen Text nicht mehr als Schwärzungskandidaten an.

- **Eigene Ausgabethemen lassen sich speichern und teilen.** Die aktuelle
  Mischung aus Ersatztext, Schwärzung und Wasserzeichen erhält einen Namen,
  bleibt in den Einstellungen und kann als klartextfreies JSON exportiert
  oder importiert werden. Die Schwarzweiß-Druckvorschau warnt vor schwachen
  Kontrasten; optionales Erfolgs-Konfetti bleibt rein in der Oberfläche.

- **Eine letzte Exportprobe und eine erklärende Prüfauflage schließen die
  Darstellungsrunde ab.** Vor dem endgültigen Speichern vergleicht Maskuro
  jede wertgenau bekannte PDF-Stelle nochmals in Textschicht und gerenderten
  Bildpunkten; Warnungen nennen ausschließlich Seite und Koordinaten. Im
  Editor zeigt *Warum ist das verdeckt?* Kategorie, Erkennungsweg und
  Sicherheitsrand, niemals den entfernten Klartext und nie im Enddokument.

- **Schwärzungsbalken dürfen jetzt hübsch sein.** Unter *Einstellungen →
  Darstellung* stehen Farbvorgaben, freie Farbwähler, Verläufe, Regenbogen,
  Streifen, Punkte, Blumen, Sterne, Herzen, Pfoten, Wolken, Blitze,
  Kaffeebohnen, Enten, Sonnen, Blätter, Schneeflocken, Papier-, Textmarker-,
  Klebeband- und reproduzierbare Zufallsmuster samt unmittelbarer Vorschau
  bereit. Ersatztexte bekommen wahlweise eine Farbe, einen Verlauf, einen
  Regenbogen, eine Pille oder ein Etikett. Kategorienfarben unterscheiden
  Namen, Adressen, Kontakte und medizinische Angaben. PDF übernimmt die
  vollständige Gestaltung; Word, PowerPoint,
  OpenDocument und HTML verwenden die gewählte deckende Grundfarbe. Der
  Schutz ändert sich dabei nicht: Maskuro entfernt den vertraulichen Inhalt
  zuerst und zeichnet Farbe oder Muster erst auf die leere Stelle.

- **Maskuro gibt es wieder für Linux – als AppImage, DEB, RPM und portables
  Archiv.** DEB und RPM tragen Programmeintrag, Dateizuordnungen,
  Terminalbefehl und Symbol ins System ein; das AppImage läuft ohne
  Installation. Aktualisierungen bleiben bei einer bestehenden DEB- oder
  RPM-Installation im selben Paketformat und bevorzugen sonst das AppImage.

- **Die Sichtprüfung legt gewöhnlichen PDF-Text nicht mehr ein zweites Mal
  als neue Treffer vor.** Der abschließende OCR-Blick und der sichere
  Neuaufbau der sichtbaren Seiten bleiben vollständig aktiv; als neue
  Fundquelle gelten in der Vorgabe aber nur Bereiche, die Seitentext und
  Einzelbild-Prüfung noch nicht gelesen haben. Damit werden Produktzeilen
  nicht allein wegen einer abweichenden zweiten OCR-Lesung zu neuen Namen
  oder Firmen. Wer weiterhin zwei unabhängige Urteile über den gesamten
  sichtbaren Text möchte, schaltet in den Einstellungen *Die gesamte
  sichtbare PDF-Seite nochmals auf Angaben prüfen* ein.

- **PDFs lassen sich fortlaufend, blattweise oder als Doppelseite ansehen.**
  Drei kompakte Ansichtsicons sitzen unten direkt neben „Breite“ und „Seite“.
  Fortlaufend
  rollt am Blattrand zur nächsten Seite; Einzelseite hält das Mausrad auf dem
  aktuellen Blatt; Doppelseite zeigt einen Bogen, macht das angeklickte Blatt
  bearbeitbar und bewegt Vor/Zurück um einen ganzen Bogen. Seitenminiaturen
  und Vergleichslupe öffnen außerdem in einer deutlich schmaleren linken
  Grundspalte und lassen der Arbeitsseite mehr Platz.

- **Sie sehen jetzt, was die KI-Stufe getan hat.** Nach jedem Lauf steht
  unter „Details" je Datei eine Zeile dazu – „KI-Stufe: 12 Grenzfälle
  geprüft, 3 verworfen" –, und wenn sie nichts zu ändern fand, steht auch
  das da. Bisher schwieg die teuerste Stufe vollständig: Ob sie überhaupt
  gefragt wurde, war von außen nicht zu erkennen.

  Wer es genauer braucht, schaltet unter „Einstellungen → KI" *Jede
  KI-Frage im Protokoll mitschreiben* ein. Dann hält die Protokolldatei je
  Frage Größe, Dauer und Anzahl der Befunde fest, dazu die Wartezeit durch
  eine Mengengrenze der Gegenstelle. Der Knopf „Protokolldatei zeigen"
  daneben öffnet den Ordner – er liegt im Anwendungsdatenverzeichnis, das
  unter Windows versteckt ist und das von sich aus niemand findet. In der
  Datei stehen ausschließlich Größen, nie Text aus Ihren Dokumenten.

- **Maskuro erkennt, wenn Ihr KI-Dienst die Anzahl der Anfragen deckelt.**
  Gehostete Dienste lassen oft nur wenige Anfragen je Minute zu – vier ist
  keine Seltenheit. Die überzähligen werden nicht abgewiesen, sondern
  müssen warten, und aus zwei Sekunden je Antwort werden vierzig. Das sah
  bisher aus, als sei das Modell langsam. Jetzt liest Maskuro die Grenze
  aus der Antwort des Dienstes, schickt nicht mehr Fragen gleichzeitig, als
  angenommen werden, nennt die Grenze unter „Verbindung prüfen" und rechnet
  sie in die Dauerschätzung ein.

- **Die Seitenansicht benutzt Ihr Word, Excel und PowerPoint – und ist
  dabei rund sechsmal schneller.** Bisher brauchte sie LibreOffice, das auf
  den wenigsten Bürorechnern steht; wer keines hatte, sah einen Knopf, der
  nach einer Fremdinstallation verlangte. Jetzt gilt: Ist Microsoft Office
  installiert, wird es von selbst benutzt – ohne Einrichtung, ohne
  Download, ohne dass Sie etwas anhaken. LibreOffice bleibt der zweite Weg
  und bei OpenDocument-Dateien sogar der erste; scheitert der eine, wird
  der andere versucht.

  Der Unterschied ist vor allem beim Arbeiten zu merken: Nach jeder
  Ersetzung wird die Seite neu gesetzt, und das kostet über Office rund
  eine halbe Sekunde statt drei. Die erste Ansicht eines Dokuments dauert
  weiterhin ein paar Sekunden, danach folgt sie Ihren Handgriffen ohne
  Wartezeit.

  Ihr eigenes geöffnetes Word wird dabei nicht angerührt: Maskuro startet
  eine eigene, unsichtbare Sitzung, öffnet die Datei nur lesend, schaltet
  Makros ab und beendet alles wieder, sobald das Nachbessern-Fenster
  zugeht. Kennwortgeschützte Dateien werden abgewiesen, statt in einem
  unsichtbaren Dialog hängen zu bleiben.

- **Die Ersteinrichtung fragt jetzt auch nach Gesichtern, Codes und
  Unterschriften – und lädt alles Fehlende in einem Zug.** Neben der
  erweiterten Erkennung stehen auf der ersten Seite die drei Bild-Schalter:
  Gesichtsbereiche unkenntlich machen, Strich- und QR-Codes unkenntlich
  machen, handgeschriebene Unterschriften auf PDF-Seiten schwärzen. Die
  PDF-Grenze steht sichtbar am Haken; Office-Dateien werden nicht
  automatisch nach Unterschriften durchsucht. Unter den Haken steht, wie
  viele Megabyte der Klick auf „Weiter“ kostet. Geladen wird danach in
  **einem** Fenster mit **einem** Fortschrittsbalken über alles zusammen,
  statt in mehreren Dialogen nacheinander; ein Abbruch beendet den ganzen
  Vorgang und lässt nichts Halbes liegen. Wer nichts davon will, nimmt die
  Haken heraus – dann wird auch nichts geladen.

- **Die Vorschau lässt sich nach Prüfbedarf ausdünnen und nach Art
  zuklappen.** Über der Liste sitzt ein Regler *Gut belegte ausblenden*: Je
  weiter er nach rechts steht, desto mehr blendet er von Grün in Richtung Rot
  aus; ganz rechts steht nur noch, was das Programm allein geraten hat. Ein
  Klick auf die Überschrift einer Art klappt sie zu. Beides ist eine
  Lesehilfe, keine Auswahl – was ausgeblendet oder zugeklappt ist, bleibt
  angehakt und wird ersetzt; wie viele Werte das gerade sind, steht unter dem
  Regler. Bei kurzen Listen erscheint der Regler nicht. Das Umschalten auf
  zwei Spalten hält jetzt außerdem auch die Schalter *nie wieder*.

- **Die Bilderliste kann sich vor jedem Lauf von selbst öffnen.** Wer über
  jedes Bild einzeln entscheiden will, setzt unter „Bilder" den neuen Haken
  *Vor jedem Lauf einzeln festlegen*. Die Liste mit Vorschau erscheint dann
  beim Bereinigen von selbst, statt dass Sie „Einzeln festlegen …" jedes Mal
  selbst anklicken; brechen Sie sie ab, wird auch nicht bereinigt. Enthält
  keine der gewählten Dateien ein Bild, erscheint nichts. Voreingestellt ist
  der Haken aus.
- **Maskuro findet auf PDF-Seiten handgeschriebene Unterschriften und
  entfernt sie aus den Bildpunkten.** Bisher blieb der Namenszug unter einem bereinigten
  Dokument stehen – die Texterkennung liest Druckschrift, und was sie
  nicht liest, wird nicht ersetzt. Die Suche ist ein eigener Schalter und
  braucht ein Erkennungsmodell, das einmalig nachgeladen wird.

  Sie findet gemessen rund 84 von 100 Unterschriften und deckt sie zu
  etwa vier Fünfteln ab. Das ist eine Hilfe und keine Zusage: Nach jedem
  Lauf steht im Bericht, wie viele gefunden wurden – und auch dann, wenn
  es keine war, denn das kann heißen, dass keine da ist oder dass eine
  übersehen wurde. Auf 72 echten Geschäftsseiten ohne Unterschrift hat
  sie keine erfunden.

  Eine **gezeichnete** Unterschrift wird gefunden, aber nicht entfernt:
  Sie besteht aus Linien, nicht aus Bildpunkten, und ein Balken darüber
  wäre nur eine Abdeckung, unter der die Linien stehen blieben. Solche
  Stellen werden gezählt und genannt, damit man sie im
  Nachbessern-Fenster selbst schwärzen kann.

  Word-, Excel-, PowerPoint- und OpenDocument-Dateien werden nicht
  automatisch nach Unterschriften durchsucht. Oberfläche, Ersteinrichtung,
  Modelldownload, Kommandozeile und Handbuch nennen diese Grenze jetzt
  ausdrücklich.

- **Der Rundgang führt jetzt auch durch die Vorschau – das Fenster, in dem
  Sie entscheiden.** Beim Übungsdokument geht es von selbst auf, auch wenn
  Sie die Vorschau sonst ausgeschaltet haben (Ihre Einstellung bleibt, wie
  sie ist). Erklärt wird, was die Farben bedeuten, warum in jeder Zeile nur
  eine Frage steht – ist da überhaupt eine Person? – und wozu „nie wieder"
  gut ist. Bei den Farben liegt das Schlaglicht auf einer gut belegten
  Zeile, meist der IBAN – dem grünen Beispiel, das der Satz nennt; danach
  auf der am schwächsten belegten, und dort dürfen Sie mitten in der
  Erklärung selbst klicken: Haken weg, der Wert bleibt im Dokument stehen.
  Bei einer langen Liste geht das Fenster für die Führung größer auf, damit
  die Erklärung nicht auf den Zeilen liegt. Geht das Fenster ein zweites Mal auf,
  sagt der Rundgang auch, warum – die fertige Seite wird noch einmal als
  Bild gelesen, und dabei entstehen Bruchstücke, die wie ein Name aussehen.

- **Der Editor geht beim ersten Mal groß auf.** Original, Ergebnis,
  Werkzeugleiste und Trefferliste stehen nebeneinander und hatten in der
  bisherigen Grundgröße zu wenig Platz. Wer das Fenster kleiner zieht,
  bekommt seine Größe beim nächsten Mal wieder – überstimmt wird niemand.

- **Ein Doppelklick auf einen Platzhalter holt ihn zurück** – in Word,
  Excel, PowerPoint, OpenDocument, Text, E-Mail und HTML. Und wer über
  mehrere Platzhalter zieht und „Auswahl zurückholen" wählt, holt alle
  darin liegenden auf einmal zurück. Man muss die eckige Klammer also
  nicht mehr genau treffen. Platzhalter, die beim Anonymisieren für
  mehrere verschiedene Werte stehen, bleiben davon ausgenommen – sie
  werden gezählt und genannt, nicht geraten.

- **Das Handbuch hat ein Kapitel „Vorschau vor dem Ersetzen".** Das
  Fenster ist vorbelegt an und ist das einzige, in dem Sie entscheiden –
  im Handbuch stand es bisher nur im Nebensatz. Jetzt steht dort, was ein
  Haken bedeutet (er gilt für **jede** Fundstelle, nicht nur die
  aufgeführte), warum je Zeile nur eine Frage zu beantworten ist, was
  „nie wieder" dauerhaft bewirkt, und warum das Fenster bei einer PDF ein
  zweites Mal aufgehen kann. In allen achtzehn Sprachen, und in der Liste
  der Einstellungen ist der Schalter jetzt ebenfalls aufgeführt.

### Geändert

- **Das Fach „Ersetzte Werte“ hat einen Regler über die Farben, und der
  Lernmodus steht dort nicht mehr.** Bei mehr als acht Werten sitzt über der
  Liste derselbe Regler wie im Vorschaufenster: *Gut belegte ausblenden*
  dünnt die Anzeige auf das aus, was wirklich nachzusehen ist. Am Dokument
  ändert das nichts, und wie viele Zeilen von wie vielen zu sehen sind, steht
  darunter – Suchfeld und Regler zählen zusammen. Der Haken *Lernmodus* ist
  aus dem Fach verschwunden; er steht weiterhin im Menü *Werkzeuge* und in
  der Werkzeugleiste.

- **Das Fach „Ersetzte Werte“ zeigt jetzt dieselben Farben wie das
  Dokument.** Jede Zeile darin ist so hinterlegt wie die Stelle im
  Dokument und wie der Wert in der Vorschau: Rot heißt „allein geraten,
  hier lohnt der zweite Blick zuerst“, Grün „von einem benannten Muster
  erkannt“. Innerhalb jeder Art steht das Unsicherste oben – Sie arbeiten
  die Liste also von oben nach unten durch und haben das Wichtigste
  zuerst gesehen. Bisher stand dort alles gleich hell und nach dem
  Alphabet sortiert.

- **Der Lernmodus ist ab Werk aus.** Nach einer Korrektur im
  Nachbessern-Fenster fragte das Programm bisher von sich aus, ob daraus eine
  eigene Regel werden soll. Diese Frage kommt mitten in der Arbeit; wer sie
  nicht bestellt hat, empfindet sie als Unterbrechung. Wer die Regeln haben
  will, schaltet den Knopf *Lernmodus* in der Werkzeugleiste ein – die Wahl
  gilt dann dauerhaft, in beide Richtungen.

### Behoben

- **Exportierte Regeldateien werden jetzt ausdrücklich als schutzwürdig
  gekennzeichnet.** Eigene Begriffe und Ausnahmen können darin im Klartext
  stehen; außerdem kann die Datei das Hash-Salz enthalten, mit dem sich
  vermutete Werte bestätigen lassen. Der erfolgreiche Export zeigt deshalb
  einen Warnhinweis und fordert dazu auf, die Datei zu schützen und nur
  bewusst an berechtigte Empfänger weiterzugeben.

- **Die letzte Sicherheitsprüfung hält bereinigte Bürodateien nicht mehr
  wegen ihrer eigenen Platzhalter zurück.** Ein Artkürzel wie „SVNR“ steht
  auch in `[SVNR1]`; bisher galt das als angeblicher Klartextrest und die
  fertige Datei wurde verworfen. Zugleich werden Rufnummern und IBANs jetzt
  auch dort nachgezogen, wo Office dieselbe Angabe ohne sichtbare Leerzeichen
  in einem Verweis oder einer eingebetteten Datei ablegt.

- **Word, Excel, PowerPoint und OpenDocument lassen keine erst spät
  entdeckte Feldkopie mehr stehen.** Wird ein Wert erstmals in einer
  Nebenablage oder eingebetteten Bürodatei erkannt, räumt ein enger Nachlauf
  auch die zuvor gelesenen sichtbaren und verborgenen Kopien auf. Bereits
  erzeugte Verweis-Platzhalter werden dabei nicht noch einmal ersetzt.

- **Beim einzelnen Zurückholen einer Word-Auswahlliste kommt keine
  benachbarte Auswahl mehr ungefragt mit zurück.** Der vollständige
  Originalabsatz wird erst übernommen, wenn auch seine Attribute keine
  offenen Platzhalter mehr enthalten.

- **Schlecht lesbare Scans verlieren weniger zusammengehörige Angaben.**
  Eine alternative OCR-Lesart mit Anrede und zweigliedrigem Namen bleibt
  erhalten; Straßenfragment, Hausnummer und PLZ-Ort schützen gemeinsam die
  ganze Anschriftszeile, auch wenn sie in benachbarte OCR-Blöcke zerfällt.
  Rechnungs- und Artikelfelder sowie Veranstaltungszeilen daneben werden
  dabei nicht mitgenommen. Ein hinter „geboren“ in mehrere OCR-Wörter und
  Satzzeichen zerfallenes gültiges Datum wird ebenfalls vollständig
  unkenntlich gemacht.

- **Das Erfolgs-Konfetti ist beim automatischen Öffnen des Editors jetzt
  sichtbar.** Die Schnipsel sprühen direkt aus dem *Bereinigen*-Knopf statt
  vom oberen Fensterrand zu regnen. Der Editor wartet nur auf den ersten,
  850 Millisekunden kurzen Sprühstoß und öffnet danach automatisch; ohne
  aktiviertes Konfetti gibt es weiterhin keine Verzögerung.

- **Seitenzähler und Zoomleiste springen beim Überfahren der Ansichtsicons
  nicht mehr hin und her.** Qt verteilte den freien Raum der Statuszeile neu,
  sobald dort der Hinweis eines Symbols erschien. Beide Bediengruppen behalten
  jetzt beim Hover ihre natürliche Breite und feste Position.

- **Die Geschwindigkeitsmessung eines angebundenen KI-Servers schlug immer
  fehl** – auf jedem Server, seit es die eigene KI gibt. Sie fragte mit
  einer engen Antwortgrenze und versuchte anschließend, die dadurch
  abgeschnittene Antwort zu lesen; das musste misslingen, und gespeichert
  wurde „nicht gemessen". Die Folgen waren überall zu sehen: Die
  Dauerschätzung rechnete Ihren Server mit dem Tempo des beigelegten
  Modells auf einem Bürorechner, und in den Einstellungen stand dauerhaft,
  die Geschwindigkeit sei noch nicht gemessen. Gemessen wird jetzt an der
  Menge, die der Server erzeugt hat, und nicht am Inhalt seiner Antwort.

- **„Maximale Erkennung (KI) – langsam" stand auch dann da, wenn es nicht
  stimmte.** Beschriftung und Hinweis beschrieben das beigelegte Modell auf
  einem Bürorechner – „ein Sprachmodell auf diesem Rechner", „bei großen
  Dokumenten bis zu einer Stunde". Wer einen eigenen KI-Server angebunden
  hat, las dort zweierlei Falsches: Gerechnet wird nicht auf seinem
  Rechner, und geantwortet wird in Sekunden statt in Stunden. Beides kommt
  jetzt aus der Messung. Liegt keine vor, behauptet die Anwendung nichts
  mehr, sondern sagt, dass noch nicht gemessen wurde.

- **Zurückholen wirkt jetzt auch auf eine gezogene Auswahl.** Wer über
  mehrere Platzhalter zog und *Auswahl zurückholen* drücken wollte, fand
  den Knopf grau: Er ging nur an, wenn die Markierung **genau** ein
  Platzhalter war – über einen Absatz gezogen ist sie das nie. Der Weg
  dahinter gab es schon, nur kam niemand hin. Jetzt genügt es, den Bereich
  zu markieren; alle Platzhalter darin kommen in einem Zug zurück.

- **Zurückholen stürzte ab, wenn die Vergleichslupe offen war.** Die Lupe
  merkt sich die Stelle unter dem Mauszeiger, um im Original mitzulaufen.
  Beim Neuladen nach einer Rücknahme gab sie diese Stelle in einer Form
  zurück, mit der die Textansicht nichts anfangen konnte – und weil so ein
  Fehler mitten in der Oberfläche das Programm beendet, war aus der
  Rücknahme ein Absturz geworden. Die Lupe steht in der Grundstellung
  offen, es traf also den gewöhnlichen Weg.

- **Nach dem Zurückholen springt die Ansicht nicht mehr an den
  Dokumentanfang.** In einem längeren Schreiben war nach jedem Handgriff
  die Stelle weg, an der man gerade arbeitete. Jetzt bleibt der Absatz
  oben stehen, der vorher oben stand.

- **Ohne LibreOffice sagt die Seitenansicht, woher es kommt, statt nur zu
  fehlen.** Die beiden Knöpfe *Seitenansicht* und *Als PDF schwärzen* waren
  gesperrt und nannten im Tooltip nur, dass kein LibreOffice gefunden wurde;
  einen Weg dorthin gab es nirgends in der Anwendung. Ein Klick öffnet jetzt
  einen Hinweis mit dem Weg zum kostenlosen, quelloffenen LibreOffice.
  Handbuch und FAQ standen an dieser Stelle falsch – sie kündigten einen
  Baustein zum Nachladen an, den die Anwendung nicht anbietet.

- **Vor dem Ausliefern wird die fertige Datei ein letztes Mal ganz
  durchsucht – jetzt auch bei Word, Excel, PowerPoint, LibreOffice, E-Mail,
  HTML und Text.** Bisher hatte nur das PDF diesen letzten Blick. Alle
  Prüfungen davor sehen an einer Stelle nach, die vorher jemand benannt
  hat; eine Ablage, an die niemand gedacht hat, prüft deshalb auch niemand.
  Zum Schluss wird nun stumpf nach allem gesucht, was ersetzt wurde – in
  jedem Teil des Pakets. Bleibt etwas stehen, entsteht **kein** Ergebnis,
  und die Meldung nennt den Wert. Eine Datei, die für bereinigt gehalten
  wird, ist schlimmer als gar keine.

- **In `<script>` und `<style>` stehende Namen werden jetzt gemeldet.**
  Beide bleiben weiterhin unangetastet – dort steht Programmtext, und eine
  Ersetzung mitten in einem Bezeichner macht aus einer Webseite eine
  kaputte Webseite. Gesagt wurde es aber bisher nicht, und das war der
  Fehler: Eine Stilregel `content: "Anna Musterfrau"` steht dem Empfänger
  **sichtbar** auf dem Schirm, und im Ergebnis stand sie weiter da, während
  das Programm die Seite als bereinigt meldete.

- **In den Einstellungen lassen sich die Zusatzmodelle wieder laden und
  entfernen.** Der Knopf neben „Erweiterte Erkennung“ und „Maximale
  Erkennung (KI)“ endete beim Drücken im Fehlerbericht-Fenster, statt das
  Modell zu holen. Der zweite Weg – der Haken in der Erkennung, der von
  selbst nach dem Modell fragt – war davon nie betroffen.

- **In Blatt- und Bereichsnamen einer Tabelle steckende Namen werden jetzt
  gemeldet.** Der Name eines Blattes steht auf dem Reiter unten, der Name
  eines benannten Bereichs im Namensfeld und in jeder Formel, die ihn
  benutzt. Ersetzt werden beide weiterhin nicht – Formeln verweisen über
  sie, und eine Mappe mit Bezugsfehlern hilft niemandem –, aber es steht
  jetzt dort. Bisher kam die Meldung nur für den Blattnamen einer
  Excel-Mappe: Ein benannter Bereich „Bezuege_Brunnthaler" ging still mit
  hinaus, und bei einer LibreOffice-Tabelle schwieg das Programm ganz. Ein
  Blatt „Notizen Ortner" galt damit als bereinigt, und der erste Blick des
  Empfängers fiel auf den Namen.

  Gemeldet wird dabei nur, was auch wirklich auf eine Person führt: ein
  Wort, das in derselben Mappe ohnehin ersetzt wurde, oder ein Treffer, der
  aus mehreren Wörtern eines auswählt. Ein alleinstehendes Wort wie
  „Zustaendig" oder „Bezug_Umsatz" löst keine Warnung mehr aus – vorher
  hätte es das getan, und eine Warnung, die bei jeder zweiten Mappe kommt,
  liest nach der dritten niemand mehr.

- **„Original zurückholen" holt jetzt wirklich alles zurück.** In manchen
  Dokumenten fehlten danach einzelne Zeichen – aus „Seestraße 14" wurde
  „Seestraße 4", aus „An:" ein „An", aus „nordlicht-planung" ein
  „nordlicht planung" –, und einzelne Zeilen kamen gar nicht wieder. Genau
  dort ließ sich anschließend nichts mehr mit der Maus auswählen und nichts
  mehr schwärzen: Der Text stand zwar auf dem Papier, aber das Programm
  kannte ihn nicht mehr. Betroffen waren schmale Zeichen – die Eins, der
  Doppelpunkt, der Bindestrich – in Dokumenten, die jedes Zeichen einzeln
  setzen; das Übungsdokument ist eines davon.

- **Und dieselben Dokumente werden beim Bereinigen nicht mehr in ein Bild
  verwandelt.** Weil ein solches Zeichen stehen blieb, meldete die
  Nachprüfung einen Rest und die Seite wurde vorsichtshalber gerastert. Der
  Text darauf war danach nur noch ein Abbild: nicht mehr durchsuchbar, nicht
  mehr markierbar, größer in der Datei. Das Übungsdokument bleibt jetzt auf
  beiden Seiten echter Text.

- **Farbige Marken bleiben nicht mehr über zurückgeholtem Text stehen.** Wer
  eine Ersetzung rückgängig machte, sah das farbige Rechteck weiter über dem
  wiederhergestellten Wort – es behauptete „hier wurde etwas entfernt",
  obwohl dort wieder das Original stand.

- **Ein Balken verrät nicht mehr, wie lang das Wort darunter war.** Beim
  Schwärzen deckt der Balken in kurzen Zeilen jetzt die **ganze** Zeile –
  Anschriftenblock, Kopfdaten, schmale Tabellenzelle. Passt die ganze Zeile
  nicht (die gewöhnliche Tabellenzeile mit drei Spalten), bleibt es beim
  Feld; in einer Fließtextzeile bleibt es wortgenau, sonst machte ein Name
  mitten im Satz den ganzen Satz schwarz. Und Balken, die untereinander
  stehen, werden **gleich lang**: Im Anschriftenblock steht auf jeder Zeile
  ein Wert, und drei verschieden lange Balken verrieten weiter, wie lang die
  Zeilen waren. Sie wachsen dabei nur so weit, wie das Papier frei ist – vor
  einer Nachbarspalte hört der Balken auf.

- **„Ganze Zeile" schwärzt jetzt wirklich die ganze Zeile.** Bisher endete
  der Balken an der nächsten größeren Lücke – also am Ende des Feldes. In
  Fließtext fiel das nicht auf, dort ist das Feld die Zeile; in Kopfdaten
  und Tabellen schon: Aus „Name: Anna Musterfrau   Abteilung: Vertrieb"
  wurde ein Balken, der genau am letzten Buchstaben des Namens endete – und
  damit stand dessen Länge wieder auf dem Blatt. Der Balken läuft jetzt vom
  ersten bis zum letzten Wort der Zeile und nimmt die Nachbarspalten mit.
  Wer nur den Wert treffen will, wählt „Wörter"; die Automatik schwärzt
  unverändert feldweise.

- **Vor dem Ausliefern wird die fertige Datei ein letztes Mal durchsucht.**
  Alle bisherigen Prüfungen sehen an einer Stelle nach, die vorher jemand
  benannt hat – Seitentext, Fundrechteck, Bildfläche. Ein PDF hat aber mehr
  Ablagen, als eine Aufzählung fassen kann: Anmerkungen, Formularwerte,
  Lesezeichen, Dokumentinformationen, Dateianhänge, JavaScript. Zum Schluss
  durchsucht Maskuro deshalb die geschriebene Datei stumpf nach allem, was es
  ersetzt hat – überall außer im Seitentext, wo derselbe Wortlaut auch erlaubt
  stehen darf. Bleibt dort etwas stehen, entsteht **kein** Ergebnis, und die
  Meldung nennt den Wert. Ein Dokument, das für bereinigt gehalten wird, ist
  schlimmer als gar keines.

- **Was sich nicht prüfen ließ, gilt nicht mehr als geprüft.** Auf drei Wegen
  sah bisher ein Fehlschlag der Nachprüfung wie ein sauberes Ergebnis aus. Eine
  Seite, deren Textebene sich nicht lesen ließ, galt als besonders sauber –
  dort war ja nichts zu finden; sie wird jetzt gerastert. Ließ sich eine Seite
  mit verbliebener Fundstelle nicht ersatzweise rastern, wurde sie
  stillschweigend ausgeliefert; jetzt bricht die Bereinigung lieber ab. Und die
  Gegenprobe im Nachbessern-Fenster meldete nach einem eigenen Fehler „nichts
  übrig" – im Fenster nicht davon zu unterscheiden, dass alles entfernt wurde;
  jetzt erscheint die Warnung samt Knopf „Seite rastern".

- **„Auf Vorgabe zurücksetzen" setzte die meisten Einstellungen gar nicht
  zurück.** Neun von zweiundzwanzig Haken standen nach dem Handgriff
  unverändert da – darunter die Vorschau, „Bereinigte Dateien danach
  öffnen", das Nachbessern-Fenster, das sofortige Ablegen und beide
  Aktualisierungshaken. Die gespeicherte Datei war zwar geleert, aber das
  Fenster hielt die alten Werte fest und schrieb sie beim nächsten Klick
  wieder hinein. Jetzt kommt jeder Haken zurück, und der Vermerk „geändert"
  verschwindet mit ihm.
- **„Prüfbericht je Bereinigung automatisch ablegen" zeigte an, war aber
  aus.** Nach dem Zurücksetzen blieb der Haken gesetzt, während der Wert
  gelöscht war – es entstand kein Bericht mehr, ohne dass etwas darauf
  hinwies. Dasselbe galt für das Prüfprotokoll und die eigene
  Bildschirmaufnahme; deren Tastenkürzel wird beim Zurücksetzen nun auch
  gleich richtig an- oder abgemeldet.

- **Die Balken einer Zeile sehen jetzt gleich aus.** Bisher brachte jede
  Fundstelle ihren eigenen Balken mit, und seine Höhe kam aus der Schrift des
  getroffenen Wortes. In einer Zeile mit Beschriftung und Wert in
  verschiedenen Größen standen deshalb ein dicker und ein dünner Strich mit
  versetzten Kanten nebeneinander, und wo zwei Fundstellen nur ein
  Leerzeichen trennte, blieb darüber ein heller Spalt. Balken derselben
  Zeile haben jetzt dieselbe Ober- und Unterkante, und was nur ein
  Leerzeichen trennt, wird ein Balken. Was zwischen zwei Fundstellen stehen
  bleiben soll – das Komma hinter dem Namen, eine Beschriftung, ein Betrag –
  hält sie weiterhin auseinander. Gilt für gesetzte Seiten wie für Scans.

- **Die Reiter unter „Über dieses Programm" beginnen wieder oben.**
  Datenschutz, Lizenzbedingungen und Lizenzhinweise gingen mitten im
  Text auf – wer sie las, musste erst ganz nach oben rollen, um die
  erste Zeile zu sehen.

- **Der Stift öffnet kein zweites Editorfenster mehr, sondern holt das
  vorhandene nach vorn.** Bisher entstand bei jedem Klick ein neues. Das
  Fenster hat keinen eigenen Eintrag in der Taskleiste – wer es minimierte,
  kam nicht mehr heran und klickte noch einmal; beim Wiederherstellen des
  Hauptfensters kamen dann alle angesammelten Fenster auf einmal nach vorn.
  Jetzt landen weitere Dokumente in der Reiterleiste des offenen Fensters,
  und ein Dokument, das dort schon steht, bekommt keinen zweiten Reiter.

- **„Erweiterte Erkennung" trägt nicht mehr den Vermerk „geändert",
  solange ihr Modell fehlt.** Ausgeliefert wird sie eingeschaltet, ohne das
  nachladbare Modell kann sie es aber gar nicht sein – in den Einstellungen
  stand die Zeile deshalb auf jedem frisch eingerichteten Rechner als
  verändert da, obwohl niemand sie angefasst hatte. Warum der Haken aus ist,
  sagt jetzt allein seine Beschriftung: „Modell noch nicht geladen".

- **Der Einführungsstreifen erklärte in Office- und Textdateien die
  PDF-Leinwand.** Dort stand „ein Wort anklicken schwärzt es" – in einer
  Word-Datei schwärzt ein Klick aber nichts, dort wird markiert und dann
  ein Knopf gedrückt. Er sagt jetzt, was in der jeweiligen Ansicht gilt.
- **Die Werkzeugleiste war in der Textansicht mit Beschriftungen
  zugestellt.** „Auswahl ersetzen", „Auswahl schwärzen", „Auswahl
  zurückholen", „Seitenansicht" und „Als PDF schwärzen" stehen jetzt als
  Symbol da – wie ihre Geschwister in einem PDF. Ihre Namen bleiben in
  Kurzhilfe und Menü.
- **Strg+Mausrad in der Vergleichslupe bewegte ihren Zoomregler nicht
  mit.** Die Schrift wurde größer, Regler und Prozentzahl daneben
  behaupteten weiter den alten Stand.
- **Das Installationsprogramm einer Aktualisierung kam nicht in den
  Vordergrund** – man musste es erst in der Taskleiste anklicken (nur
  Windows).
- **Eine Jahreszahl am Zeilenanfang galt als österreichische
  Postleitzahl.** In einem Lebenslauf wurde aus „2020 Verkaufsstrategien"
  ein Platzhalter – die ganze Zeile verschwand. Eine vierstellige Zahl
  zwischen 1900 und 2099 braucht jetzt ein zweites Anschriftsignal:
  die Straße darüber, ein Feldwort davor, eine Länderkennung oder einen
  bekannten Ortsnamen. Anschriftenblöcke haben das; Jahresspalten nicht.
- **Ein Monat-Jahr-Paar galt als Telefonnummer.** Aus „Seit 08.2010
  123-Verkauft GmbH" wurde eine „Rufnummer" – Monat, Jahr und die ersten
  Ziffern des Firmennamens dahinter.
- **Der Bericht sagte „per Texterkennung geprüft" und verschwieg, was
  sie nicht liest.** Bleiben Bilder erhalten, steht jetzt dabei, dass
  Handschriftliches darin nicht gefunden wird – eine Unterschrift oder
  ein handschriftlich eingetragener Name bleibt stehen. Bisher stand
  dieser Satz nur bei gescannten Seiten; ein gewöhnliches PDF mit einer
  eingebetteten Unterschrift bekam kein Wort darüber.
- **Ein Platzhalter auf geschwärztem Bildgrund stand am linken Rand
  seines Balkens.** Wird ein Wert in einem Bild gefunden – etwa ein
  getippter Name neben einer eingescannten Unterschrift –, muss der
  Bildbereich in voller Breite geschwärzt werden. Der kürzere Platzhalter
  ließ daneben nacktes Schwarz stehen, was nach zwei Vorgängen aussah. Er
  sitzt jetzt mittig auf dem Balken.

## 0.10.41-alpha.20260826 – 26. August 2026

### Neu

- **Nach dem Testzeitraum erinnert ein Fenster einmal je Start an die
  Lizenz.** Es kommt fünf Minuten nach dem Start – nicht sofort, damit es
  niemandem vor dem ersten Handgriff im Weg steht – und wartet ab, solange
  eine Bereinigung läuft. Von dort führt ein Weg zum Kauf und einer zum
  Eintragen eines schon gekauften Schlüssels; „Später" schließt es, sobald
  die fünf Sekunden im Knopf abgelaufen sind. Gesperrt wird nichts: Die
  kostenlose Stufe arbeitet weiter wie bisher.

- **Die Wartezeit vor einem Lauf in der kostenlosen Stufe dauert jetzt zehn
  statt dreißig Sekunden.** Sie soll an die Lizenz erinnern, nicht die
  Arbeit anhalten.

- **Alle drei Hinweise zur Lizenz sehen jetzt gleich aus.** Wartezeit,
  Erinnerung in den letzten Testtagen und Hinweis nach dem Testzeitraum
  tragen denselben Streifen, denselben Aufbau und dieselben Knöpfe; die
  Restzeit steht dabei im Knopf statt als große Zahl daneben.

- **Die Trefferliste in der Vorschau steht wieder untereinander.** Sie war
  ab neun Werten zweispaltig; beim Durchgehen springt das Auge dabei zwischen
  zwei Bahnen, und entschieden wird hier Zeile für Zeile. Wer die zwei Bahnen
  mag, schaltet sie unten links im Fenster wieder ein – die Wahl bleibt
  gespeichert, und beim Umschalten bleiben bereits abgewählte Werte
  abgewählt.

- **Die KI-Stufe steht jedem offen, der einen eigenen KI-Server anbindet.**
  „Einstellungen → KI" trägt alles dazu: die Anbindung, was die KI tun darf,
  was sie zu tun bekommt – und darüber den Schalter für die Stufe samt
  Gegenprobe, sobald ein Server eingetragen ist. Ein Sprachmodell, das auf
  dem eigenen Arbeitsplatz mitrechnet, bleibt zurückgehalten: Es braucht für
  zehn Seiten mehrere Minuten und ist damit nichts für den Alltag.

- **Eine eigene KI lässt sich anbinden.** Statt des beigelegten
  Sprachmodells kann ein größeres Modell auf einem anderen Rechner antworten –
  auf einem Server im Haus oder einer Arbeitsstation mit starker Grafikkarte.
  Verlangt wird ein Dienst mit OpenAI-verträglicher Schnittstelle (Ollama, LM
  Studio, llama.cpp-server, vLLM, LocalAI); eingerichtet wird er unter
  „Einstellungen → Eigene KI" samt Verbindungsprüfung, die das Modell wirklich
  befragt, das Tempo misst und die mögliche Antwortform feststellt. Mehrere
  Textabschnitte laufen dabei gleichzeitig statt nacheinander.

- **Was die KI tun darf und was sie zu tun bekommt, ist jetzt einstellbar.**
  Drei Schalter entscheiden über Grenzfallprüfung, eigenständiges Suchen und
  Suchen im Fließtext; die Anweisung an das Modell steht wörtlich da, lässt
  sich um Haus-Begriffe ergänzen und mit einem Knopf auf die Vorgabe
  zurücksetzen.

- **Verlässt der Text dabei das eigene Netz, wird vor jedem Lauf gewarnt.**
  Maskuro erkennt an der Adresse, ob der KI-Server im Haus steht, und nennt
  einen bekannten Anbieter beim Namen. Die Warnung lässt sich abstellen, aber
  nur gegen die ausdrückliche Bestätigung, zu dieser Übermittlung befugt zu
  sein, und nur für genau diese Adresse. Am Vorgang ändert das nichts: Die
  Übertragung steht weiterhin im Protokoll und im Prüfbericht jeder Datei.
  Auf der Kommandozeile wird nicht gefragt, sondern angehalten – dort braucht
  es `--ki-auswaerts-erlauben`.

- **Die Vorschau vor dem Ersetzen ist bei neuen Einstellungen standardmäßig
  aktiv und gilt nun auch für ausdrücklich bereinigte Zwischenablage-Inhalte
  sowie Text und Bilder, die ins Programm eingefügt werden.** Bei Dokumentstapeln
  erscheint weiterhin genau eine Vorschau je Dokument mit allen Seiten; die
  stille Sofortbereinigung kurzer Kopien öffnet bewusst kein Fenster.

- **Treffer lassen sich in der Vorschau über die ganze farbige Zeile ein-
  und ausschalten.** Der Haken ist nun groß und kontrastreich; zusätzlich
  zeigt ein Zustandsfeld „Ersetzen“ bzw. durchgestrichen „Ersetzen“, sodass
  ausgewählte und abgewählte Werte auch auf dunklen Konfidenzfarben sofort
  auseinanderzuhalten sind.

- **Auch PDFs mit sichtbarem Sicherheits-Gegenblick öffnen die Vorschau nur
  noch einmal pro Dokument.** Abgewählte Begriffe bleiben für den späteren
  Seitenzeugen abgewählt; dessen Prüfung läuft weiter, ohne denselben Lauf
  mit einem zweiten Dialog zu unterbrechen.

- **Ersatzwörter sehen im Nachbessern-Editor auch auf gerasterten Seiten
  gleich aus.** Liegt der rote Platzhalter in den Bildpunkten statt in der
  PDF-Textebene, bekommt er nun trotzdem dieselbe nach Konfidenz gefärbte
  Hintergrundfläche wie ein gewöhnlicher PDF-Textplatzhalter.

- **Schon die Vorschau vor dem Ersetzen zeigt den Prüfbedarf der gefundenen
  Begriffe.** Jede Zeile trägt dieselbe Rot–Orange–Grün-Farbe wie später der
  Ersatz im Editor. Innerhalb einer Kategorie stehen geringe Sicherheit und
  rote Fehlalarmkandidaten oben, starke grüne Belege unten; Gleichstände
  bleiben alphabetisch. Kommt derselbe Wert aus mehreren Fundstellen, zählt
  vorsichtshalber deren fraglichste Bewertung. Unbewertete Sonderfälle stehen
  neutral gelb zwischen Rot und Orange.

- **Das Ergebnis lässt sich jetzt direkt aus dem Nachbessern-Editor als
  Datei kopieren.** „Ergebnis kopieren“ legt die aktuelle bereinigte Fassung
  in die Zwischenablage, ohne den Editor zu schließen und die Datei in der
  Hauptliste wiederzusuchen. Bei einer noch nicht gespeicherten
  Handbearbeitung läuft davor automatisch der vollständige sichere
  Speicherweg; „Bild kopieren“ bleibt als getrennte Funktion für reine
  Bildpunkte erhalten.

- **Ersetzte Wörter zeigen im Editor auf einen Blick, was zuerst geprüft
  werden sollte.** Reine Sprachmodell-Raterei ist rot, auch wenn spaCy dafür
  pauschal 85 Prozent meldet. Weitere ungestützte Modellurteile bleiben
  höchstens orange; starke benannte Belege können grün werden. Handarbeit und
  ältere Zuordnungen ohne auswertbare Bewertung bleiben neutral gelb. Auch
  automatische Schwärzbalken tragen diese Farben in der Editorvorschau – nun
  auch dann, wenn der Balken Teil einer gerasterten PDF-Seite ist. Dafür muss
  die Zuordnung passen und der frühere Wortkasten nachweislich deckend schwarz
  sein; gewöhnlicher Fettdruck wird nicht eingefärbt. In der gespeicherten PDF
  bleiben alle Balken unverändert deckend schwarz.

- **Was in der Vorschau abgewählt wird, lässt sich dauerhaft merken.** Wo Sie
  den Haken wegnehmen, sagen Sie: Hier hat sich die Erkennung geirrt. Bisher
  galt das nur für dieses eine Dokument. Jetzt erscheint an der Zeile ein
  Schalter „nie wieder"; gedrückt kommt der Wert dauerhaft in die Liste
  „Nie entfernen" und gilt künftig in jedem Dokument als unbedenklich. Unter
  der Liste steht, was dabei dauerhaft wird, bevor Sie „Ersetzen" drücken.
  Die Gegenrichtung gibt es bewusst nicht: Was einmal gefunden wurde, findet
  die Erkennung wieder.

- **Ein Knopf setzt alle Einstellungen auf den Auslieferungsstand zurück.**
  Er steht unten links im Einstellungsfenster und fragt vorher nach. Ihre
  Dateien, Ihre Lizenz, Ihre eigenen Erkennungsregeln und der Autostart
  bleiben unberührt; was Ihre Verwaltung vorgibt, gilt weiter. Jede
  Einstellung, die vom Auslieferungsstand abweicht, trägt außerdem den
  Vermerk „geändert" – so sieht man auf einen Blick, was man verstellt hat.

### Geändert

- **Ein Ergebnis wird nicht mehr von selbst abgelegt – erst beim Speichern.**
  Ein Lauf aus dem Fenster schreibt seine bereinigte Fassung zunächst an
  einen vorläufigen Ort; die Datei „…_bereinigt“ neben dem Original entsteht
  erst, wenn Sie „Speichern“ drücken. Bis dahin lässt sich das Ergebnis
  ansehen, nachbessern und kopieren. Jede fertige Zeile hat dafür einen
  Speichern-Knopf, unter der Liste steht „Alle speichern“, und im Editor
  gilt Strg+S. Wer die Liste leert oder das Programm beendet, wird gefragt;
  was niemand ablegt, bleibt auch nirgends liegen. „Im Ordner zeigen“ ist
  vor dem Speichern gesperrt – der vorläufige Ort ist kein Ziel, an das man
  jemanden schickt. Die Zuordnungsdatei geht beim Speichern mit.

  In den Einstellungen unter „Programm“ holt „Ergebnisse sofort neben dem
  Original ablegen“ das bisherige Verhalten zurück. Kommandozeile,
  Ordnerwache und Zwischenablage-Wächter legen unverändert sofort ab – dort
  sitzt niemand, der speichern könnte.

- **Die Werkzeugleiste des Nachbessern-Editors ist aufgeräumt.** Der
  Lernmodus steht jetzt am rechten Ende bei Vergleichslupe und „Ersetzte
  Werte“ – die drei Schalter, die eine Betriebsart ein- und ausschalten,
  stehen damit beieinander. „Auf alle Seiten übertragen“ ist zu den drei
  Schwärzungsformen gerückt, weil es nur dort etwas tut. „Ergebnis
  kopieren“, „Datei – Zurücksetzen“ und „Auf alle Seiten übertragen“ kommen
  ohne Beschriftung aus; ihr Name steht weiterhin im Tooltip und im Menü.
  Zwischen „Ersetzen“ und „Original zurückholen“ steht ein Trennstrich: Die
  beiden sind Gegenrichtungen und sahen nebeneinander aus wie zwei
  Spielarten desselben Werkzeugs.

- **Das Symbol für „Ergebnis kopieren“ zeigt jetzt ein Dokument.** Zwei
  Blätter mit geknickter Ecke und Textzeilen statt zweier gleicher Blätter
  mit einem kleinen Eckpfeil. „Bild kopieren“ trägt im Gegenzug das
  Bildzeichen, damit beide ohne Beschriftung auseinanderzuhalten sind. Der
  Knopf „Kopieren“ in der Ergebnisliste zeigt dasselbe Dokumentsymbol – er
  legt dieselbe Datei ab.

- **Die Einstellungen sind sortiert und mit Überschriften versehen.**
  „Erkennung" hat jetzt vier Abschnitte: *Was entfernt wird*, *Wie ersetzt
  wird*, *Wie gründlich gesucht wird* und *Vor und nach dem Lauf*.
  Gesichtserkennung und Strich-/QR-Codes stehen bei den Bildern, wo man sie
  sucht; „Programm" ist in *Ergebnisdateien*, *Beim Start*, *Aktualisierung*,
  *Anzeige* und *Rückmeldung an uns* geteilt, und der Namenszusatz der
  Ergebnisdatei steht bei den Ergebnisdateien statt zwischen Sprache und
  Erscheinungsbild.

- **Die erweiterte Erkennung ist ab Werk eingeschaltet**, auch bevor ihr
  Sprachmodell geladen ist. Vorher hing die Vorgabe am Modellbestand, und ein
  frisch eingerichteter Rechner lief dauerhaft auf der schwächeren Stufe. Das
  Einrichten-Fenster bietet das Modell auf der ersten Seite zum Laden an und
  nennt den Preis daneben. Fehlt es, sagt der Haken das weiterhin, statt eine
  Stufe vorzutäuschen, die nicht läuft.

- **Die zwei Begriffslisten heißen jetzt, was sie tun:** „Immer entfernen"
  statt „Eigene Begriffe" und „Nie entfernen" statt „Ausnahmen".

- **Das Vorschaufenster ist übersichtlicher.** Ab neun Werten stehen sie in
  zwei Spalten, die Zeilen sind flacher, und die Anzahl der Fundstellen steht
  direkt hinter dem Begriff statt am rechten Rand.

- **Im Nachbessern-Editor steht Ersetzen vor Schwärzen** – in der
  Werkzeugleiste, im Menü „Werkzeuge" und im Rechtsklick auf der Seite.
  Ersetzen ist der Regelfall: Ein Platzhalter lässt sich anklicken und
  zurückholen, ein Balken nicht.

- **Weniger doppelte Knöpfe im Editor.** „Speichern unter …" und „Bild
  kopieren" stehen nur noch im Datei-Menü, mit ihren gewohnten Tastenkürzeln.
  In der Leiste bleibt je einer: Speichern und „Ergebnis kopieren" – wohin
  gespeichert wird, steht ohnehin in der Statuszeile und lässt sich dort mit
  einem Klick ändern.

- **Der Zwischenablage-Wächter wird beim ersten Start nicht mehr angeboten.**
  Er greift in jeden Kopiervorgang des Systems ein; wer das Programm zum
  ersten Mal sieht, kann das nicht abschätzen. In den Einstellungen steht er
  weiter, dort mit der Klausel daneben, die zu ihm gehört.

- **Das helle Erscheinungsbild blendet weniger.** Der Fenstergrund kam bisher
  vom jeweiligen Systemstil und war damit die einzige große Fläche, die
  niemand entschieden hatte – unter Windows nahezu Weiß. Jetzt ist er ein
  gebrochenes Weiß, auf jedem System gleich.

- **Der Rundgang und das Handbuch erklären die Farben.** Was Rot, Orange,
  Grün und Gelb hinter einem ersetzten Wert bedeuten, steht jetzt als eigene
  Station im Rundgang und als Absatz im Handbuch – in allen Sprachfassungen.

### Behoben

- **Handbuch und FAQ zeigten Platzhalter, die es nicht mehr gibt.** Seit der
  Umstellung auf die kurze Form schreibt Maskuro `[NAM1]`; in der Hilfe stand
  weiterhin `[NAME1]`, und der Satz „Voreingestellt ist `[NAME1]`" war damit
  schlicht falsch. In den siebzehn übersetzten Fassungen stand zusätzlich die
  **deutsche** Marke statt der eigenen – ein spanischer Leser sah `[NAME1]`,
  wo sein Programm `[NOMB1]` schreibt. Ebenso die Endung der Ergebnisdatei:
  Dort versprachen alle Fassungen `_bereinigt`, während das Programm
  `_limpiado`, `_nettoyé` oder `_除去済み` anlegt. Betroffen waren auch die
  nummernlose Form (beim Anonymisieren heißt alles `[NAM]`, nicht `[NAME]`)
  und die aus dem Wert abgeleitete Kennung beim Hashen.

- **Das Vorschaufenster unterbricht nur noch einmal je Dokument – und ein
  zweites Mal nur, wenn wirklich etwas Neues dazukommt.** Eine PDF wird von
  zwei Seiten gelesen: einmal aus dem Inhaltsstrom und zuletzt von der
  gerenderten, sichtbaren Seite. Bisher fragte jeder der beiden für sich.
  Jetzt gilt: Was Sie im ersten Fenster entschieden haben, gilt weiter, und
  Werte, die dort schon standen, kommen nicht wieder. Findet die
  Sichtprüfung der fertigen Seiten dagegen etwas, das vorher nirgends stand,
  bekommen Sie es noch einmal vorgelegt – allein, ohne die schon
  entschiedenen Werte.

- **Das Vorschaufenster sagt jetzt, wonach man entscheiden soll.** Statt
  „Haken entfernen = der Wert bleibt stehen" – was der Haken *tut*, aber
  nicht, wann man ihn wegnehmen soll – steht dort: Haken weg überall dort,
  wo kein personenbezogener Wert steht; dort hat sich die Erkennung geirrt.
  Außerdem nennt jedes Fenster den Prüflauf, aus dem seine Werte stammen.

- **Platzhalter sehen im ganzen Dokument gleich aus.** Auf Seiten, die im
  OCR-Weg als Bildseiten neu aufgebaut werden, wurden sichtbare Platzhalter
  bisher in Schreibmaschinenschrift gesetzt – „[PLZ4]“ stand dann breit und
  mit Serifen neben einem schmalen „[NAM1]“ derselben Seite. Sie tragen
  jetzt dieselbe serifenlose Schrift wie überall sonst und werden auch nicht
  mehr breiter gesetzt, als beim Einpassen geplant war. Die unsichtbare
  Suchschicht behält ihre eigene Schrift – sie braucht verlässliche Maße,
  kein Aussehen.

- **In der Werkzeugleiste des Editors stehen keine doppelten Trennstriche
  mehr.** Wo eine ganze Werkzeuggruppe für die geöffnete Dateiart entfällt –
  in einem PDF etwa Seitenansicht und Rendern –, blieben bisher beide
  Striche um die Lücke herum stehen.

- **Beim Zurückholen bleibt nicht mehr gelegentlich nur eine weiße Stelle
  zurück.** Ein bereits exakt wiederhergestellter Originaltext wird nicht
  mehr durch den breiten, zusammengefassten Kasten seines entfernten
  Platzhalters weiß übermalt. Bei gemischten Text- und Bildrückholungen wird
  Text außerdem nur dann unsichtbar eingesetzt, wenn das Seitenbild genau
  diesen Originalstand bereits sichtbar trägt. Das gilt für Rahmen,
  Trefferpanel und PDF-Anhänge.

- **„Original zurückholen“ bietet nicht mehr unnötig an, die Seite zu
  rastern.** Die strenge Resttextprüfung bleibt beim Schwärzen und Ersetzen
  aktiv. Beim Zurückholen wird sie ausgelassen: Dort kommt Originalinhalt
  bewusst wieder hinzu, und unveränderte Nachbarwörter im erweiterten
  Rückholrahmen waren kein Bereinigungsfehler, sondern ein Fehlalarm.

- **Der Rundgang durch den Editor erklärt „Ersetzen“ und „Original
  zurückholen“ jetzt als eigene Schritte.** Beide Werkzeuge werden direkt in
  der Leiste hervorgehoben und beschreiben, dass ein gezogener Rahmen einen
  Platzhalter einsetzt beziehungsweise den ursprünglichen Inhalt dieser
  Stelle aus der Quelldatei zurückholt.

- **Auch länderspezifische Platzhalter bleiben jetzt bei höchstens vier
  Buchstaben.** Diese Arten fehlten bisher im zentralen Kürzelkatalog und
  konnten deshalb noch ausgeschrieben erscheinen, etwa
  `[UMSATZSTEUER_ID1]`. Neue Läufe schreiben dafür `[UID1]`; alle
  automatisch erkannten deutschen und englischen Arten bleiben dabei
  eindeutig. Selbst berechnete Kürzel anderer Oberflächensprachen wachsen
  bei Namensgleichheit nicht mehr über vier Zeichen hinaus. Eigene
  Regelbeschriftungen bleiben unverändert so benannt, wie sie eingegeben
  wurden.

- **Ersetzen nutzt jetzt den ganzen tatsächlich freien Zeilenraum, bevor es
  schwärzt.** Die bisherige starre Grenze beim Dreifachen der ursprünglichen
  Wortbreite erzeugte selbst in weitgehend leeren Formularfeldern Balken.
  Auch Treffer des sichtbaren OCR-Gegenblicks bekommen bei belegtem PDF-Text
  nun einen lesbaren Platzhalter; schwarz bleiben reine Bild-, Annotations-
  und Vektorinhalte, die gewählte Schwärzbetriebsart sowie echte Engstellen,
  in die nicht einmal eine eindeutige Kurzform passt.

- **Ein bereits sichtbarer Platzhalter wird beim Sicherheits-Rastern nicht
  mehr ein zweites Mal rot darübergeschrieben.** Die Rasterung übernimmt den
  vorhandenen Ersatz jetzt aus dem Seitenbild und legt nur eine unsichtbare
  Suchkopie an. Muss ein Sicherheitsbalken genau diese Stelle übermalen, wird
  der ganze tatsächliche Platzhalterkasten erneuert statt nur sein kürzerer
  ursprünglicher Anker.

- **„Original zurückholen“ markiert nur noch sichere Ziele im gezogenen
  Rahmen.** Alle ersetzten Begriffe darin leuchten einzeln und exakt auf;
  unveränderter Fließtext bleibt unangetastet. Echte vektorielle
  Schwärzbalken werden ebenfalls einzeln markiert, wenn unter ihrer schwarzen
  PDF-Fläche Originaltext liegt. Bei gerasterten Seiten verzichtet die
  Vorschau bewusst auf eine vermeintliche Balkenfläche: Die frühere
  Bildpunktsuche verband dort Buchstaben, Unterstreichungen und Tabellenlinien
  zu großen roten Flächen an falschen Stellen. Die Wiederherstellung selbst
  bleibt davon unberührt.

- **Beim Wiederherstellen auf gerasterten Seiten kommt der Text wieder
  zurück.** Zuletzt blieb dort eine leere Stelle mit farbigen Rechtecken
  darüber. Der zurückgeholte Text stand im Dokument, wurde aber vom weißen
  Grund eines Platzhalters übermalt, der weiter hinten im Seitenaufbau
  gezeichnet wird.

- **Die Prüffarben liegen nicht mehr mehrfach übereinander.** Dieselbe Stelle
  wurde je Eintrag der Zuordnung eingefärbt – auf einer Seite fünf echte
  Fundstellen, jede fünffach übermalt, bis aus der blassen Marke ein satter
  Block wurde. Und sie erscheinen nicht mehr auf Wörtern, die gar nicht
  ersetzt wurden: Steht der Originalwert noch auf der Seite, gibt es dort
  auch keine Marke mehr.

## 0.10.40-beta.1 – 24. August 2026

### Behoben

- **Schwärzbalken im Editor besitzen jetzt einen Sicherheitsrand.** Wort-,
  Zeilen- und freie Rahmen decken auch überhängende Glyphen und geglättete
  Randpixel ab; eine Renderprüfung sichert zusätzlich ab, dass weder sichtbare
  Reste noch auslesbarer Originaltext stehen bleiben.

- **Ersatztexte bleiben lesbar und einheitlich kurz.** Neue Namen, Adressen
  und freie Begriffe erscheinen beispielsweise als `[NAM1]`, `[ADR2]` und
  `[BEG3]`. Die feste Untergrenze beträgt 4,5 Punkt; bei Platzmangel wird
  zuerst gekürzt und der nutzbare Laufraum erweitert. Alte Zuordnungen mit
  langen Platzhaltern bleiben les- und rückholbar.

- **Mehrwortige Ersetzungen aus dem Trefferpanel sind gegen doppelte Marken
  und Originalreste abgesichert.** Die Regression besteht mit und ohne
  nummerierte Platzhalter; je Fundstelle bleibt genau eine gemeinsame
  Zuordnung erhalten.

- **Zurückgeholte Zwischenablage-Inhalte werden auf macOS nicht sofort
  erneut bereinigt.** Auch wenn die Systemsignatur nach dem Schreiben erst
  verzögert wechselt, erkennt Maskuro den eigenen Inhalt zuverlässig.

### Neu

- **Der Editor kann eine Datei vollständig auf die frisch bereinigte
  Ausgangsfassung zurücksetzen.** „Datei – Zurücksetzen“ verwirft nach einer
  Bestätigung sämtliche Nachbesserungen des aktuellen Reiters einschließlich
  Ersetzungsliste und Zählern. Der Befehl ist ohne Änderungen gesperrt und
  lässt sich seinerseits mit „Rückgängig“ wieder zurücknehmen.

- **Verschobene Datumsangaben behalten ihre Chronologie jetzt verlässlich
  über mehrere Dateien.** Der gemeinsame Versatz wird schon beim Einschalten
  der Strategie dauerhaft in den Regeln verankert; außerdem kann der Versatz
  nicht mehr null Tage betragen und damit unbemerkt das echte Datum stehen
  lassen.

- **Die PDF-Handarbeit deckt jetzt den vollständigen professionellen
  Schwärzungsablauf ab.** Einzelbegriffe, Listen und reguläre Muster lassen
  sich im geöffneten PDF oder über alle PDFs eines Ordners suchen und sicher
  schwärzen; ganze Seiten und Seitenbereiche sind direkt wählbar. Farbe,
  neutral weiße Fläche, Überlagerungstext, Schrift, Ausrichtung und
  Wiederholung besitzen eine Vorschau, wiederverwendbare Codes lassen sich
  verwalten sowie im- und exportieren. Die PDF-Bereinigung entfernt wahlweise
  alle verborgenen Inhalte durch vollständigen Neuaufbau oder ausgewählte
  Datenklassen. Die sicherste Wahl ist klar empfohlen, ungültige Suchmuster
  werden erklärt und Ordnerläufe schreiben ausschließlich Ergebniskopien.

- **Die freiwillige Nutzungsstatistik zeigt nun Installationen und
  Fassungswechsel.** Maskuro erzeugt dafür eine zufällige, örtlich gespeicherte
  Installationskennung. Sie enthält keine Geräte-, Benutzer- oder
  Lizenzangaben; der Server speichert nur ihren SHA-256-Wert. Die Statistik
  bleibt in den Einstellungen vollständig abschaltbar.

- **Der Rundgang ist jetzt eine geführte Übung durch beide Fenster.** Er
  legt das erfundene Übungsdokument selbst in die Liste, erklärt den Weg bis
  zum Bereinigen und setzt sich nach dem Lauf automatisch im Editor fort.
  Wer den Rundgang abbricht, beendet auch diese Fortsetzung.

- **Firmen aus fünfzehn weiteren Rechtsräumen werden erkannt.** Wer
  Unterlagen aus dem Baltikum, Belgien, Skandinavien, Tschechien, Polen,
  Südosteuropa, Singapur, Brasilien oder Mexiko bereinigt, verliert
  Firmennamen nicht mehr, weil ihre Rechtsform unbekannt war – neu dabei
  sind unter anderem OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k., EIRELI, z.s.,
  o.p.s., S.K.A., Pte. Ltd. sowie S.A. de C.V. und S. de R.L.

### Geändert

- **Die Editor-Werkzeugleisten nutzen ihren Platz jetzt gezielter.**
  Eindeutige Standardsymbole und direkt erkennbare Werkzeugformen stehen ohne
  wiederholenden Text in der Leiste; mehrdeutige Handlungen behalten ihren
  Namen. Unter „Ansicht“ kann „Werkzeugbeschriftungen anzeigen“ ausgeschaltet
  werden, um beide Leisten vollständig auf Symbole zu reduzieren. Tooltips
  und Menüs bleiben dabei vollständig beschriftet, die Wahl wird gemerkt.

- **Der Lernmodus ist jetzt dauerhaft in der Werkzeugleiste sichtbar.** Er
  lässt sich dort unmittelbar ein- und ausschalten, auch wenn das Fach der
  ersetzten Werte geschlossen ist. Werkzeugleiste, Werkzeuge-Menü und der
  bisherige Haken im Fach zeigen stets denselben Zustand.

- **„Zurücksetzen“ an der Vergleichslupe setzt nur noch deren Zoom
  zurück.** Der Knopf stellt die Vorgabe von 125 Prozent wieder her, ohne die
  Lupe anzudocken, zu verschieben oder ihre Fenstergröße zu verändern. Für
  den gesamten Aufbau bleibt „Ansicht zurücksetzen“ zuständig.

- **Fehler und Wünsche lassen sich jetzt auch über den Hilfe-Knopf
  melden.** „Fehler melden …“ und „Wunsch äußern …“ stehen dort nun genauso
  wie im klassischen Hilfe-Menü; beide Wege öffnen die bereits vorhandene
  sichere Fehlermeldung beziehungsweise die öffentliche Wunschliste.

- **Das Taskleistenmenü ist kürzer und klarer geordnet.** Die beiden Befehle
  mit globalem Tastenkürzel – Zwischenablage-Bereinigung und Bildschirmfoto –
  stehen nun unmittelbar untereinander mit einer gemeinsamen rechten
  Kürzelspalte. „Letzten Originalinhalt wiederherstellen“ entfällt dort; der
  verständlichere Wiederherstellen-Knopf bleibt im Hauptfenster verfügbar.

- **Rechtliche Seiten sind unmittelbar unter „Hilfe → Rechtliches“
  erreichbar.** Das Untermenü führt zu Lizenzbedingungen,
  Datenschutzerklärung, Impressum und AGB auf maskuro.com. Hinweise zum
  Widerruf bleiben beim Kauf auf der Website.

- **Von Hand geschwärzte PDFs werden beim Speichern vollständig neu
  aufgebaut.** Sichtbar bleiben die Seiten und ihre neu gelesene
  Suchschicht; Metadaten, Dateianlagen, Lesezeichen, Kommentare,
  Formularwerte, versteckte Ebenen, Suchindizes, Skripte, zugeschnittene
  Inhalte und unter anderen Objekten verborgene Inhalte werden nicht in die
  Ausgabedatei übernommen. Schrift und Vektorgrafik bestehen danach aus
  Bildpunkten – das ist der Preis der beweisbaren Grenze zum fremden
  PDF-Objektbaum.

- **Strg+Umschalt+B nimmt jetzt auf allen Systemen standardmäßig ein
  Bildschirmfoto mit Maskuro auf.** Die Drucktaste und Kombinationen damit
  bleiben als eigene Belegung möglich. Im Menü des Taskleistensymbols stehen die globalen
  Tastenkürzel jetzt rechts neben den zugehörigen Befehlen. Eigene
  gespeicherte Belegungen bleiben erhalten.

- **Der Editor startet mit Seiten und Vergleichslupe links.** Das Seitenfach
  steht oben, die geöffnete Original-Lupe direkt darunter; die ersetzten
  Werte bleiben rechts. Eine bewusst gespeicherte eigene Anordnung hat weiter
  Vorrang.

- **Das Übungsdokument steht nicht mehr dauerhaft im Hauptfenster.** Es ist
  Teil der geführten Übung und bleibt zusätzlich unter „Hilfe“ erreichbar.

- **Der Erststart führt unmittelbar zur praktischen Übung.** Die bebilderte
  Kurzanleitung wird nicht mehr als zweiter, inhaltlich doppelter Einstiegsweg
  angeboten; sie bleibt jederzeit unter „Hilfe → Kurzanleitung“ erreichbar.

- **Das ruhende Taskleistensymbol bleibt in voller Farbe.** Es zeigt jetzt
  dasselbe kräftige Maskuro-Schild wie der aktive Zwischenablage-Modus; nur
  bei aktiver Überwachung kommt der grüne Leuchtpunkt hinzu.

- **Das Übungsdokument bleibt in Maskuro.** Der Einstiegsknopf erzeugt das
  erfundene PDF und fügt es direkt in die Dateiliste ein, startet aber keinen
  zusätzlichen PDF-Betrachter mehr.

- **Die Suche im Nachbessern-Fenster bleibt beim Tippen flüssig.** Der Platz
  für den Trefferzähler wird schon beim Öffnen reserviert; sein erster Text
  verändert die Leinwand nicht mehr und löst keinen neuen PDF-Rasterlauf aus.

- **Herstellernamen in Fabrikatsangaben bleiben sichtbar.** Ein Eintrag wie
  „Fabrikat: TRILUX oder gleichwertig“ beschreibt die benötigte Ware und
  wird nicht mehr allein wegen dieser Beschriftung als Firma geschwärzt.
  Lieferanten-, Firmen- und Herstellerfelder bleiben davon unberührt.

- **Korpusmessungen zählen zu weit geschwärzte Treffer als Fehlalarme.** Wenn
  Maskuro den erwarteten Namen entfernt, dabei aber einen Satzteil mitnimmt,
  steigt jetzt die Fehlalarmzahl. Der Bericht weist Übergriffe zusätzlich
  getrennt aus; frühere Fehlalarmzahlen sind daher nicht direkt vergleichbar.

### Behoben

- **Technische und behördliche Begriffe aus deutschen Originalunterlagen
  werden seltener als Namen oder Orte geschwärzt.** Fahrzeugausstattungen,
  Positions- und Summenzeilen, Vergabe- und Datenschutzbegriffe,
  Gesetzesverweise sowie Dateinamen öffentlicher Materialien werden nur mit
  ihrem belegten Sachkontext ausgebremst. Ein bei der Texterkennung verlorener
  Umlaut in „Marz 2026“ bleibt als Monat geschützt; „Marz“ ohne Datumsbezug
  kann weiterhin ein echter Name oder Ort sein.

- **„Original zurückholen“ nimmt sofort die vollständige benötigte Breite.**
  Trifft der Rahmen nur ein Wort eines zugeordneten Werts, erweitert Maskuro
  ihn anhand der Zuordnung und der Originalzeile selbstständig auf die ganze
  Angabe – etwa von „Planungs“ auf „Nordlicht Planungs GmbH“. Der anschließend
  greifbare Rahmen zeigt ebenfalls die tatsächlich zurückgeholte Gesamtbreite.

- **„Original zurückholen“ zeigt schwarze Balken jetzt als eindeutiges
  Ziel.** Beim Darüberfahren oder Ziehen leuchtet der ganze erkannte Balken
  rot mit heller Kontrastkontur auf, statt nur ein kaum zuzuordnender
  Textkasten daneben. Das gilt auch für gerasterte Seiten, auf denen der
  Balken nur noch aus Bildpunkten besteht.

- **Der Editor-Rundgang lässt keine Stationen mehr aus, wenn Fächer
  geschlossen waren.** Für die Führung öffnet und ordnet Maskuro Seitenfach,
  Vergleichslupe und ersetzte Werte vorübergehend selbst. Nach „Fertig“ oder
  einem Abbruch kehrt die persönliche Anordnung zurück. Ist ein Werkzeug bei
  einer Dokumentart grundsätzlich nicht verfügbar, bleibt seine Erklärung
  als Texthalt erhalten, statt unbemerkt zu verschwinden.

- **„Ersetzen“ bleibt auch beim PDF-Sicherheitsrückfall sichtbar.** Musste
  Maskuro eine Seite wegen eines verbliebenen Zeichens oder beschädigten
  Textlaufs als Bild neu aufbauen, standen die richtigen Ersetzungen nur noch
  unsichtbar in der Suchschicht und auf der Seite lagen schwarze Balken. Die
  tatsächlich gesetzten Ersatzwerte werden nun über alle Raster- und
  OCR-Neuaufbauten hinweg sichtbar rot und durchsuchbar erhalten.

- **Die Hinweise oberhalb der bereinigten Fassung bleiben im dunklen
  Erscheinungsbild lesbar.** Fassungsüberschrift, Bedienzeile und Einführung
  übernehmen ihre Schriftfarbe jetzt unmittelbar vom tatsächlich
  dargestellten Qt-Fenster.

- **Schwärzrahmen sitzen auf gerasterten PDF-Seiten wieder über dem Text.**
  Die unsichtbaren Wortkästen waren je nach Originalschrift schmaler als die
  sichtbaren Buchstaben. Dadurch entstanden Lücken im Balken oder der letzte
  Buchstabe blieb lesbar. Die Kästen behalten nun Breite, Höhe und
  Laufrichtung des sichtbaren Wortes.

- **„Was ist neu“ beginnt wieder ganz oben.** Der Changelog-Dialog setzt nach
  dem fertigen Fensteraufbau Textcursor und Bildlaufleiste ausdrücklich an
  den Anfang, statt je nach Qt-Stand mitten in den Neuerungen zu starten.

- **Schließen während der Scan-Worterkennung bleibt still.** Ein gerade
  fertig werdender OCR-Hintergrundlauf sendet nicht mehr in ein bereits
  geschlossenes Nachbessern-Fenster.

- **Relative Zeitangaben werden nicht mehr für Namen gehalten.** Feste
  Wendungen wie „heute“, „gestern“, „morgen“ und „nächste Woche“ kennt
  Maskuro nun aus den amtlichen Kalenderdaten der jeweiligen
  Dokumentsprache.

- **Beenden während des ersten Modellladens räumt sauber auf.** Wer Maskuro
  oder das Nachbessern-Fenster unmittelbar nach dem Öffnen schließt, lässt
  keinen noch in der nativen Spracherkennung arbeitenden Faden beim
  Prozessabbau zurück. Das verhindert den sporadischen Absturzbericht beim
  Beenden; ein bereits laufendes Laden wird geordnet fertiggestellt.

- **Verzögerte Startdialoge erscheinen nicht mehr nach dem Beenden.** Wer
  das Hauptfenster kurz nach dem Start schließt, bekommt nicht anschließend
  noch unsichtbar oder verspätet die Frage nach der besten Erkennung,
  Neuerungen oder Einführung angezeigt.

- **HTML und E-Mail behalten ihre Zeilenenden.** Auf Windows mischte die
  HTML-Serialisierung nach Bereinigung und Rücknahme LF und CRLF. Inhalt und
  Formatierung waren richtig, die Datei aber nicht mehr bytegleich. HTML-
  Dateien und MIME-Nachrichten übernehmen nun wieder die Schreibweise ihrer
  Quelle.

- **Firmennamen mit einem Verhältniswort bleiben vollständig.** Hinter einem
  Fürwort schnitt Maskuro Namen wie „Gesellschaft für Systemtechnik mbH“
  oder „Bank für Arbeit und Wirtschaft AG“ am Wort „für“ ab. Der ganze
  Firmenname wird jetzt erkannt; echte Satzvorspänne wie „Wir sind bei
  Alpha GmbH versichert“ bleiben sichtbar.

- **Chinesische Firmennamen bleiben vor ihrer Rechtsform vollständig.** Ein
  als Verb deutbarer Markenbestandteil konnte trotz des eindeutigen Zusatzes
  „有限公司“ den gesamten Namen verwerfen. In Schriften ohne Groß- und
  Kleinschreibung hat der amtliche Rechtsformanker nun Vorrang vor dieser
  unsicheren Wortartgrenze.

- **PDF-Seiten wurden ohne Not zu Bildern.** Bei mehrseitigen PDFs, deren
  Seiten sich eine Schriftliste teilen – was gängige Erzeuger so anlegen –,
  verloren nach der ersten Seite alle weiteren den Verweis auf ihre
  Schriften. Die Folge war doppelt: Umlaute waren im Ergebnis nicht mehr
  durchsuchbar („Auftragsbestätigung" ließ sich nicht finden), und die
  Nachprüfung hielt daraufhin Buchstaben für übersehen, die auf der Seite
  nie standen – sie rasterte heile Textseiten zu Bildern, damit nicht mehr
  durchsuchbar, nicht kopierbar und deutlich größer. Im Prüfbestand traf
  das vier von siebzehn Seiten.
- **Ein Komma allein löst keine Rasterung mehr aus.** Endet ein
  Fundbereich am Wort, gehört das Satzzeichen daneben noch knapp hinein.
  Ein Komma oder ein Punkt ist aber keine übersehene Angabe, und die
  Rasterung kostet die ganze Seite. Buchstaben und Ziffern bleiben
  unverändert ein Grund nachzuschärfen.

## 0.10.38-alpha.20260824 – 24. August 2026

### Neu

- **Firmennamen ohne Rechtsform werden jetzt erkannt, wenn ihre
  Beschriftung sie nennt.** „Lieferant: Kranzbichler Handels GmbH" wurde
  immer schon entfernt – die Rechtsform verrät die Firma. „Lieferant:
  Dehner Märkte" blieb stehen, und in Angeboten, Ausschreibungen und
  Bestellungen steht der Lieferant meistens genau so da. Dasselbe gilt
  für „Firma:", „Hersteller:", „Fabrikat:", „Arbeitgeber:" und ihre
  Entsprechungen in acht weiteren Sprachen, und auch dann, wenn die
  Beschriftung allein in ihrer Zeile steht und der Name darunter.

  Was hinter der Beschriftung *keine* Firma ist, bleibt unangetastet:
  „Lieferant: siehe Anlage" wird nicht geschwärzt – sonst stünde dort
  „Lieferant: [ORGA1]", und das behauptete einen Namen, den es nie gab.
  Beschriftungen, hinter denen ebenso oft ein Mensch steht („Kunde:",
  „Auftraggeber:"), sind bewusst nicht dabei.

- **Ein eingesetztes Bild lässt sich jetzt auch bearbeiten.** Im Fenster
  „Bild bereinigen" steht neben „Ergebnis kopieren" ein Knopf *Im Editor
  bearbeiten*: Das Bild wird bereinigt und dann zum Nachschwärzen,
  Beschriften und Hervorheben geöffnet – derselbe Weg, den ein
  Bildschirmfoto geht.

- **Nummern hinter ihrer Beschriftung werden auch dann gefunden, wenn sie
  einen Geschäftspartner benennen.** Bisher fielen Kunden-, Vertrags- und
  Personalnummern; jetzt auch Debitoren-, Kreditoren- und
  Lieferantennummer, die österreichische Dienstgebernummer, die
  ANKÖ-Registrierung und die WEEE-, EAR- und EPR-Nummer eines Herstellers –
  auf Deutsch wie auf Englisch. Außerdem versteht Maskuro jetzt die
  Schreibweise gesetzter Angebotsköpfe mit Leerzeichen vor dem Doppelpunkt
  („Kunden-Nr : K903944“). Artikel-, Bestell-, Auftrags-, Angebots- und
  Rechnungsnummern bleiben weiterhin unangetastet: Sie benennen den Vorgang
  oder die Ware, nicht den Menschen. Wer sie doch entfernen will, hinterlegt
  sie als eigenes Suchmuster.

- **Sie sehen jetzt, wie lange eine Datei gebraucht hat.** An der fertigen
  Zeile steht die Dauer neben der erkannten Sprache („fertig · Deutsch ·
  2,4 s“), in der Zusammenfassung die des ganzen Laufs, in der
  Kennzahlen-Klappe die Summe – und im Prüfbericht steht sie als eigenes
  Feld. Bei mehreren Dateien verrät die Zeile, welche davon die Zeit
  gekostet hat.

- **Nicht von der System-OCR unterstützte Schriften können mit vorhandener
  Sprachdatei ersatzweise gelesen werden.** Bisher galt: Beherrscht
  die systemeigene Texterkennung eine Schrift nicht (auf dem Mac etwa
  Devanagari), stand im Ergebnis „Bild(er) wurden NICHT geprüft“, und die
  Angaben im Bild blieben stehen. Jetzt springt die mitgelieferte
  Texterkennung ein, wenn die passende Sprachdatei vorliegt. Weil ein so
  gelesenes Bild unsicherer ist als ein regulär geprüftes, steht das im
  Ergebnis: „mit dem Ersatzverfahren gelesen – bitte ansehen“. Gemessen an
  einem historischen Zwischenstand der Hindi-Probe: **zehn Angaben mehr
  gefunden und vier Fehlalarme weniger** (64 % → 73 %). Der aktuelle
  Abschlusswert steht weiter oben und ist damit nicht zu verwechseln.

- **Die Texterkennung fragt nach der richtigen Sprache.** Für alle
  Dokumentsprachen außer Deutsch und Englisch wurde bisher das englische
  Erkennungsmodell benutzt, auch wenn die passende Sprachdatei bereitlag.
  Unter Windows betraf das jede Sprache – Griechisch, Japanisch oder Hindi
  wurden dort mit dem englischen Modell gelesen.

- **Ein Einrichtungsassistent beim allerersten Start.** (Wer Maskuro schon
  benutzt hat, bekommt ihn nicht – „Erststart“ heißt erster Start, nicht
  erster Start nach dieser Aktualisierung.) Drei Fragen statt sechs
  Bilder: die Sprache Ihrer Dokumente, ob Text in Bildern mitgelesen wird,
  und wie Sie Maskuro im Alltag erreichen wollen. Am Ende stehen die drei
  Wege weiter – Übungsdokument, Rundgang oder die bebilderte Kurzanleitung.
  Alles lässt sich überspringen, und „Hilfe → Einrichtung erneut durchgehen“
  holt ihn zurück.

- **F1 schlägt das Handbuch beim passenden Kapitel auf.** Im Hauptfenster,
  in den Einstellungen (dort je nach Seite), im Durchsehen-Fenster und in
  der Sprachverwaltung; im Nachbessern-Fenster über Umschalt+F1, weil F1
  dort seit je die Tastenkürzel zeigt. Bisher begann die Hilfe immer oben,
  bei 25 Kapiteln.

- **Neues erstes Handbuchkapitel: „In drei Minuten loslegen“.** Vier
  Schritte, mehr braucht es für ein Dokument nicht – in allen 18
  Sprachfassungen.

- **Ein Rundgang durch das Fenster.** „Hilfe → Rundgang durch das Fenster“
  legt ein Schlaglicht auf ein Bedienelement nach dem anderen und schreibt
  einen Satz daneben – im Hauptfenster acht Stationen, im
  Nachbessern-Fenster sieben. Anders als die bebilderte Kurzanleitung
  erklärt er das Fenster, vor dem Sie gerade sitzen. Abbrechen jederzeit
  mit Esc.

- **Ein Übungsdokument zum gefahrlosen Ausprobieren.** Unter der
  Ablagefläche steht jetzt „Übungsdokument öffnen“ (auch im Hilfe-Menü). Es
  legt ein erfundenes Blatt an – Name, Anschrift, Telefonnummer, IBAN,
  Sozialversicherungsnummer – und auf dem Blatt steht zugleich, was Sie
  damit tun können und was Sie danach sehen werden. Kein Wort davon gehört
  einem echten Menschen; das erste Dokument, das Sie durch Maskuro
  schicken, muss also kein echtes sein.

- **„Nur nachsehen …“ steht jetzt neben „Bereinigen“.** Es zeigt, wo
  personenbezogene Daten liegen – Datei, Art und Anzahl –, ohne irgendetwas
  zu verändern oder zu schreiben. Wer ein Dokument abgelegt hat, sieht damit
  erst nach, bevor er bereinigt. Bisher lag dieser Weg nur im Datei-Menü
  unter „Ordner durchsehen …“ und ging über einen ganzen Ordner statt über
  die abgelegten Dateien.

- **Wenn nichts gefunden wurde, steht jetzt dabei, woran es liegen kann.**
  Etwa: In der Datei stehen Bilder, aber „Auch Text in Bildern prüfen“ ist
  aus. Oder: Die eingestellte Sprache passt nicht zu der im Dokument. Und
  wenn nichts dergleichen vorliegt, sagt Maskuro auch das.

- **Das Nachbessern-Fenster begrüßt Sie beim ersten Mal mit drei Sätzen:**
  anklicken schwärzt ein Wort, ziehen einen Bereich, rechts stehen die
  ersetzten Werte. „Verstanden“ nimmt den Hinweis dauerhaft weg;
  „Hilfe → Einführung erneut zeigen“ holt ihn zurück.

- **Wörter anklicken jetzt auch auf gescannten Seiten.** Bisher ließen sich
  Wörter nur dort anklicken, wo die PDF eine Textebene mitbringt – bei einem
  Scan ging es nicht, und im selben Dokument konnte es von Seite zu Seite
  wechseln. Solche Seiten werden jetzt einmalig von der Texterkennung
  gelesen; danach klickt man Wörter an wie überall sonst. Die Statuszeile
  sagt, was gerade passiert.

- **Das Seitenfach ist wieder eine Fläche.** Es hörte in der Mitte seiner
  Spalte auf: Titelbalken abgeschnitten, daneben ein Streifen in einer
  anderen Farbe, und die aktuelle Seite war nur an einem farbigen Kasten
  hinter ihrer Nummer zu erkennen. Jetzt füllt es seine Spalte aus, lässt
  sich breiter ziehen, und die aktuelle Seite ist als ganze Kachel
  hervorgehoben – mit unverfälschter Seitenvorschau darin.

- **Ersetzte Stellen leuchten blass gelb.** In der Seitenansicht ist damit
  auf einen Blick zu sehen, wo etwas ersetzt wurde – dieselbe Farbe, die
  die Vergleichslupe über dem Original benutzt. Der rote Rahmen beim Zeigen
  mit der Maus bleibt unverändert.

- **„Ansicht zurücksetzen“ im Nachbessern-Fenster** (Menü „Ansicht“). Wer
  Seitenfach oder Trefferliste verschoben, herausgelöst oder geschlossen
  hat, stellt damit alles wieder dorthin, wo es beim ersten Start stand.

### Geändert

- **Die Platzhalter sind kürzer.** Aus `[SOZIALVERSICHERUNGSNR_1]` wird
  `[SVNR1]`, aus `[ORGANISATION_1]` ein `[ORGA1]`, aus `[EMAIL_1]` ein
  `[MAIL1]`. Der Grund ist nicht Schönheit: Ein Platzhalter, der länger ist
  als der Wert, den er ersetzt, drängt die Zeile auseinander und findet in
  einer engen Tabellenspalte gar keinen Platz mehr – dort blieb bisher ein
  schwarzer Balken, und der sagt niemandem mehr, dass an der Stelle etwas
  stand. Wo es eine gebräuchliche Abkürzung gibt, steht sie da (`[BLZ1]`,
  `[KFZ1]`, `[IBAN1]`). Ergebnisse aus früheren Läufen bleiben nutzbar: Die
  alte Schreibweise wird weiterhin erkannt, und Zuordnungsdateien von
  gestern funktionieren unverändert.

- **Das Programmsymbol steht jetzt überall gleich da.** In der Menüleiste
  des Macs erschien bisher ein einfarbiges Schild, das das System selbst
  schwarz oder weiß färbte, in der Windows-Taskleiste ein grünes bzw. graues.
  Jetzt trägt jede Leiste dasselbe blaue Maskuro-Schild. Woran zu sehen ist,
  ob die Zwischenablage überwacht wird, bleibt gleich deutlich: Läuft die
  Überwachung, sitzt ein grüner Punkt am Schild; ruht sie, steht dasselbe
  Schild blass da. Auch in den kleinsten Größen stehen jetzt beide
  Schwärzungsbalken im Schild – bisher zeigte die Taskleiste dort nur einen.

- **Gesichter werden mit einem Modell erkannt, dessen Trainingsbilder mit
  Einwilligung entstanden sind.** Ausgeliefert wird jetzt MediaPipe BlazeFace
  (Apache-2.0); der bisherige Detektor bleibt eingebaut und umschaltbar, wird
  aber nicht mehr mitgeliefert, weil seine Trainingsherkunft nicht
  abschließend geklärt ist. Für die Erkennung ändert sich nichts: An 324
  Porträts und 143 Bildern ohne Gesicht findet die neue Fassung gleich viel
  bei gleich wenigen Fehlgriffen und braucht ein Drittel der Zeit.

- **OCR ist der Sicherheitsanker für die stärkste PDF-Zusage.** Der normale
  PDF-Lauf verwendet sie und erzeugt den vollständigen Minimalaufbau. Wer OCR
  ausdrücklich ausschaltet, erhält den kompatibleren Objektweg; Oberfläche,
  Abschlussmeldung und Handbuch sagen nun ausdrücklich, dass dieser Weg nicht
  dieselbe Architektur gegen unbekannte verborgene PDF-Kanäle bietet.

- **Das Verkaufs-Gate sperrt nun auch das bisher beigefügte YuNet-Modell.**
  Die MIT-Lizenz des exakten Gewichts bleibt dokumentiert, reicht für die
  öffentlich sichtbare Trainingsdatenkette über WIDER FACE aber nicht als
  konservative Produktfreigabe. Vor Verkauf ist eine schriftliche Klärung
  oder der Austausch gegen ein Modell mit belastbarer kommerzieller Daten-
  und Gewichtskette erforderlich.

- **Firmen- und Organisationsnamen werden jetzt von sich aus entfernt.**
  Bisher blieben sie stehen, solange man sie nicht ausdrücklich anforderte.
  Das war für einen Geschäftsbrief die falsche Vorgabe: Wer ein Angebot
  weitergibt, will den Auftraggeber nicht darin lesen. „Kranzbichler
  Handels GmbH“, „Institut für Bauphysik“ und Ähnliches wird deshalb
  behandelt wie ein Name. Wer es anders braucht, schaltet es im Fenster ab;
  auf der Kommandozeile heißt der Schalter jetzt
  `--ohne-organisationen`. Der alte `--mit-organisationen` wird
  weiterhin angenommen und tut nichts mehr, damit bestehende Skripte und
  Verknüpfungen nicht brechen. Datums- und Geldangaben bleiben unverändert
  ausgenommen.

- **Schwärzen hat jetzt drei Formen statt zweier Haken.** „Wörter“, „Ganze
  Zeile“ und „Freier Rahmen“ stehen als eine Wahl nebeneinander – es gilt
  immer genau eine. Bisher waren „Textzeilen“ und „Ganze Zeile“ zwei
  unabhängige Schalter, die beide gedrückt sein konnten, und der freie
  Rahmen war überhaupt kein Knopf, sondern der ausgeschaltete Zustand des
  ersten. Die drei stehen sichtbar bei ihrem Werkzeug und sind grau,
  solange ein anderes Werkzeug gewählt ist.

### Verbessert

- **Das erste Dokument ist rund eine Sekunde schneller fertig.** Bevor die
  Bereinigung beginnt, stellt Maskuro die Sprache des Dokuments fest – und
  holte sich dafür bisher die Wortlisten aller 48 Sprachen auf einem Weg, der
  weit mehr lud als die Wörter. Das war etwa die Hälfte der Wartezeit bis zum
  ersten Ergebnis. Die Erkennung selbst ist unverändert: Sie sieht dieselben
  Wörter wie zuvor, nur schneller. Jedes weitere Dokument war davon ohnehin
  nicht betroffen.

- **Dokumente mit sehr langen Absätzen werden schneller geprüft.** Bei einem
  Absatz ohne Zeilenumbruch las Maskuro ihn für jede gefundene Stelle erneut
  ganz durch; jetzt genügt einmal. Je länger der Absatz, desto größer der
  Unterschied – gemessen rund ein Siebtel weniger Rechenzeit. Am Ergebnis
  ändert sich nichts.

### Behoben

- **Mit einer Firma verschwand oft der halbe Satz mit.** Stand ein
  Firmenname im Fließtext – „Information über die Gottwald GmbH & Co KG",
  „… (AGB) der Musterbetriebe GmbH" –, wurde nicht nur der Name
  geschwärzt, sondern alles davor bis zum Satzanfang. Der Text wurde
  dadurch unlesbar, und es sah aus, als sei wahllos geschwärzt worden.
  Firmennamen, die selbst ein „für" oder „und" tragen („Bank für Arbeit
  und Wirtschaft AG"), bleiben dabei unverändert vollständig.

- **Firmennamen blieben in Briefköpfen stehen, obwohl sie im Text entfernt
  wurden.** In einem Angebot stand der Firmensitz im Briefkopfbild noch
  lesbar da – derselbe Ort, den Maskuro im Fließtext geschwärzt hatte; im
  durchsuchbaren Text des Ergebnisses stand er sogar unsichtbar weiter
  drin. Was einmal entfernt wurde, wird jetzt auch dort entfernt, wo es
  nur als Bild vorliegt. Das wirkt auch bei Logos und Wortzeichen, die als
  Grafik gezeichnet sind.

- **macOS fragte bei jedem Start nach der Bildschirmaufnahme**, auch wenn
  die Freigabe längst erteilt war. Der Hinweis beim Start probierte eine
  Aufnahme aus, und genau das holt den Systemdialog auf den Schirm. Jetzt
  fragt beim Start nur noch Maskuro selbst, und nur einmal; das System
  fragt erst, wenn Sie wirklich ein Bildschirmfoto aufnehmen.

- **Technische Sachbegriffe wurden für Orte und Firmen gehalten.**
  „Einspeisepunkt", „Flachdach", „Verteileranlage", „Meldersockel" und
  Dutzende ähnliche Wörter verschwanden aus Angeboten und
  Leistungsverzeichnissen. Maskuro erkennt sie jetzt an ihrem Grundwort:
  Was auf „-anlage", „-punkt" oder „-kanal" endet, ist eine Sache. Ortsnamen
  wie Berlin, Melk oder Wieselburg haben kein solches Grundwort und bleiben
  unberührt – ebenso Anschriften wie „Der Graben" oder „Alter Markt".

- **Japanische, koreanische, chinesische, thailändische und Gujarati-Dokumente
  konnten das Programm zum Absturz bringen.** Enthielt ein Dokument in einer
  dieser fünf Sprachen eine Internetadresse ohne „https://" davor, brach die
  Bereinigung mit einem internen Fehler ab – bei geöffnetem Fenster ging dabei
  auch die übrige Arbeit verloren. Alle achtundvierzig wählbaren
  Dokumentsprachen laufen jetzt durch; fehlt für eine Sprache das
  Häufigkeitswörterbuch, bleibt die Angabe im Zweifel stehen statt zu
  verschwinden.

- **Feldbeschriftungen schützten nur auf Deutsch und Englisch.** „Reference"
  blieb stehen, das italienische „Riferimento" und das portugiesische
  „Referência" wurden als Ortsangabe entfernt – derselbe Feldname, dieselbe
  Zeile, anderes Ergebnis. Wer nicht auf Englisch arbeitet, war damit
  schlechter gestellt. Maskuro kennt jetzt in allen elf gepflegten Sprachen
  dieselben Feldnamen.

- **„Original zurückholen" holte auf gescannten Seiten zu viel zurück.** Ein
  Rahmen über einer geschwärzten Zeile eines Anschriftenblocks legte den
  **ganzen Block** wieder offen – und die Seite blieb zerrissen zurück:
  Balkenreste standen noch, aus denen einzelne Wortenden ragten. Grund war,
  dass untereinanderliegende Balken auf einer gerasterten Seite aneinander
  stoßen und deshalb als eine einzige Fläche galten. Zurückgeholt wird jetzt
  genau die Zeile, auf die der Rahmen zeigt; die Nachbarzeilen bleiben
  geschwärzt, und der Balken der getroffenen Zeile verschwindet ganz.

- **Mengenangaben in Positionslisten wurden für Anschriften gehalten.** In
  einer Zeile wie „1.4  Kabelgraben  100,00  m" wurde „Kabelgraben 100" als
  Straße mit Hausnummer ersetzt. Solche Zeilen bleiben jetzt stehen; echte
  Anschriften – auch „Hauptplatz 1, 3250 Wieselburg" – werden unverändert
  erkannt.

- **Vor einem Firmennamen verschwand der halbe Satz.** Aus „Vertrag zwischen
  der Firma Gottwald GmbH & Co KG und dem Auftraggeber." wurde
  „[ORGANISATION_1] und dem Auftraggeber." – der Satzanfang war weg, und
  damit der Hinweis, worum es geht. Jetzt fällt nur noch der Firmenname
  selbst. Wo das Gattungswort zum Namen gehört („Deutsche Bank AG",
  „Universität Wien"), bleibt alles wie bisher.

- **In einem Protokoll blieben Sprecher stehen, deren Name zugleich ein
  Beruf ist.** „Bauer:", „Koch:", „Weber:" vor einer Wortmeldung wurden
  übersehen, „Gruber:" daneben nicht – Maskuro brauchte bisher mindestens
  einen erkannten Namen im Schriftstück, um die Zeilen überhaupt als
  Wortmeldungen zu lesen. Trägt das Dokument eine Überschrift wie
  „Ergebnisprotokoll" oder „Niederschrift", genügt das jetzt. Merkzeilen
  („Achtung: …", „Hinweis: …") bleiben unangetastet.

- **Eine Feldbeschriftung verschwand zusammen mit ihrem Wert.** Aus
  „Projekt: Sanierung und Erweiterung Gemeindezentrum" wurde ein einziger
  Platzhalter – auch das Wort „Projekt:" war weg, und damit der Hinweis
  darauf, was an dieser Stelle gestanden hatte. Beschriftungen bleiben jetzt
  stehen. Wo eine Beschriftung zur Angabe gehört und ihre Bedeutung trägt
  („Durchwahl 214"), ändert sich nichts.

- **Die maximale Erkennung räumte Sachbegriffe nicht ab.** „Flachdach",
  „Einspeisepunkt", „Elektrotechnik" und ähnliche Fachwörter wurden auch mit
  eingeschalteter KI-Stufe als Ort oder Firma ersetzt – die KI bekam genau
  diese Funde nie zur Beurteilung vorgelegt. Sie prüft sie jetzt mit: An
  einem Korpus aus Ausschreibungs- und Vertragstexten verschwinden dadurch
  alle 27 Fehlgriffe, ohne dass eine einzige echte Angabe stehen bleibt.
  Namen, Firmen und Orte werden unverändert erkannt.

- **Gattungswörter für Einrichtungsarten wurden für Organisationen
  gehalten.** In einem Vertragstext verschwanden „Hochschulen und
  Universitäten", „Staatliche und private Schulen", „Akademische
  Lehrkrankenhäuser", „Bildungseinrichtung" und „Zulieferfirmen" – Wörter,
  die keine bestimmte Stelle benennen, sondern eine Art von Stelle. Sie
  bleiben jetzt stehen. Steht ein Eigenname davor („EU-Kommission"), wird
  weiterhin ersetzt, und Firmennamen sind von der Regel gar nicht erfasst.

- **Namen in Listen fielen nur, wenn sie geläufig waren.** In einer
  Teilnehmer- oder Anwesenheitsliste unter einem Spaltenkopf „Name" wurden
  „Anna Huber" und „Thomas Müller" entfernt, „Wójcik Aleksandra" oder
  „Kücükgöl Sinan" aber nicht – dieselbe Zeile, derselbe Aufbau. Wer einen
  selteneren Namen trägt, war damit schlechter geschützt. Jetzt entscheidet
  der Spaltenkopf: Was unter „Name" steht, ist ein Name. Eine Positionsliste
  mit sachlichem Spaltenkopf bleibt unangetastet.

- **Eine Rufnummer hinter „Durchwahl" wurde in der Mitte durchgeschnitten.**
  Aus „Durchwahl 0732 771190" wurde „[DURCHWAHL_1] 771190" – die zweite
  Hälfte der Nummer blieb lesbar. Jetzt fällt die vollständige Nummer ganz,
  und die Beschriftung bleibt stehen. Eine echte Durchwahl („Durchwahl 214")
  wird unverändert samt Beschriftung ersetzt.

- **Manche PDFs ließen sich gar nicht mehr bereinigen.** Konnte ein
  Farbprofil oder die Metadaten in einem Bild nicht nachweislich entfernt
  werden, brach der Lauf ohne Ergebnis ab – betroffen waren gewöhnliche
  Geschäftsunterlagen wie AGB-Seiten, Lastenhefte und Ausschreibungen. Solche
  Dateien werden jetzt bereinigt, und eine Warnung nennt die Stellen, die
  offen blieben: Sie können eine Geräte-, Erzeuger- oder Aufnahmekennung
  tragen. Das Original bleibt wie immer unverändert.

- **Vertragsrollen wurden für Personen gehalten.** „Bieter", „Verbraucher",
  „Mieter", „Käufer", „Auftraggebers" und rund vierzig weitere Rollenwörter
  wurden ersetzt, wo sie ohne Artikel standen – in Vertragsüberschriften,
  Tabellenspalten und Unterschriftszeilen. Ein Vertragstext ohne ein
  einziges Personendatum wurde dadurch stellenweise unlesbar. Diese Wörter
  bleiben jetzt stehen. Steht daneben ein Personenhinweis – eine Anrede,
  ein Vorname, ein Feldwort wie „Ansprechpartner" –, wird weiterhin ersetzt:
  „Herr Bieter" und „Frau Käufer" sind Namen. Häufige Familiennamen, die
  zugleich Berufe sind (Bauer, Richter, Koch), sind von der Regel gar nicht
  erfasst.

- **Eine abgekürzt geschriebene Straße wurde übersehen, wenn die Hausnummer
  direkt am Punkt klebte.** „Schlesischestr.31" galt nicht als Anschrift –
  und weil die Postleitzahl daneben ihren Halt aus dem Adressfund bezieht,
  blieb auch sie stehen. Im Ergebnis war die Anschrift aus Straße und
  Postleitzahl wieder zusammensetzbar, und zwar nur auf manchen Seiten
  desselben Dokuments. Beides fällt jetzt zusammen. Sachbezeichnungen mit
  angehängter Zahl („Kabelrinne200") bleiben unangetastet.

- **Eine Anschrift über zwei Zeilen wurde zu einem einzigen Platzhalter
  zusammengezogen.** Stand in einem Anschriftenblock die Postleitzahl über
  der Straße, verband Maskuro beide Zeilen zu einer Fundstelle: Im Ergebnis
  verschwand der Zeilenumbruch, und die Postleitzahl blieb davor lesbar
  stehen. Jetzt wird jede Zeile für sich gefunden und ersetzt, und das
  Schriftbild bleibt erhalten. Dieselbe Ursache zog gelegentlich auch den
  Nachnamen aus der Zeile darüber in die Anschrift hinein.

- **Der maximale PDF-Weg übernimmt keine Originalobjekte mehr.** Mit
  eingeschalteter Texterkennung baut Maskuro jede Seite aus dem sichtbaren
  PDFium-Bild vollständig neu auf. In die neue Minimaldatei kommen nur diese
  Bildseite und eine neu erzeugte, auf den OCR-Text begrenzte Suchschicht – nicht der
  fremde Objektbaum mit Kommentaren, Anhängen, Aktionen, Ebenen, Metadaten,
  Farbprofilen oder privaten Schlüsseln. Das gilt auch für Inhalte in
  Annotation-Erscheinungen, Mustern, Type-3-Schriften, Formobjekten und
  Softmasks. Die Quelldatei bleibt unangetastet.

- **Gesichter und Codes in verschachtelten PDF-Grafiken wurden übersehen.**
  Beide Detektoren sehen jetzt zusätzlich das vollständige gerenderte
  Seitenbild. Dadurch erreichen auch Portraits und QR-/Strichcodes in
  Annotationen, Mustern, Type-3-Glyphen und Transparenzmasken die Detektoren;
  erkannte Bereiche werden – wenn eingeschaltet – vor dem Minimalaufbau
  unkenntlich gemacht. Die Detektion selbst bleibt fehlbar.

- **Eine fehlende OCR-Maschine endete bei PDFs mit einem internen Fehler.**
  Der maximale Lauf bricht jetzt kontrolliert und ohne Zieldatei ab, statt
  eine unvollständige oder ungeprüfte Datei auszugeben.

- **Mehrere echte Kontakt- und Geschäftswerte fielen durch, während
  Sachtext ersetzt wurde.** Namensfelder über Zeilenumbrüche, Bank- und
  Firmennamen, Rechtsformen, beschriftete Kennnummern, Geburtsdaten sowie
  Telefon-, URL- und IBAN-Grenzen sind enger geprüft. Gleichzeitig bleiben
  Länder im Sachtext, Rollen- und Gattungswörter, Artikel-/Normcodes,
  Zahlenkolonnen und gewöhnliche Abkürzungen häufiger unangetastet.

- **Gemischte und gedrehte OCR-Zeilen wurden falsch gelesen.** Unsichere
  senkrechte Wörter werden jetzt örtlich aufgerichtet nachgelesen;
  technische lateinische Werte in nichtlateinischem Text erhalten einen
  unabhängigen Englisch-Zeugen. Eine freistehende unsichere Einzelziffer wird
  nur korrigiert, wenn zwei enge Ziffernläufe übereinstimmen. Polnische
  Rechtsformen der OCR-Form „sp. z 0.0.“ werden im geschlossenen Kontext als
  „sp. z o.o.“ gelesen.

- **Die Bildmessung konnte teilweise sichtbare Restwerte übersehen.** Sie
  prüft nun überlappende örtliche Ausschnitte, unterscheidet weiße
  Platzhalterschrift auf einem schwarzen Balken von Originalglyphen und
  überträgt Rohbildkästen auch auf gedrehte, neu gerenderte Minimal-PDFs.
  Der feste synthetische Hauptkorpus erreicht damit 1.392/1.392 entfernte
  Sollangaben bei 0 Fehlalarmen und 0 Verarbeitungsfehlern. Das ist ein
  Korpusnachweis, kein allgemeines 100-%-Versprechen.

- **Nichtkommerzielle Sprachmodelle werden nicht mehr angeboten.** Die sechs
  italienischen und griechischen spaCy-Varianten unter CC BY-NC-SA 3.0 sind
  aus Katalog, Download und Ladeweg entfernt; auch bereits vorhandene
  Modellordner werden ignoriert. Beide Sprachen verwenden stattdessen das
  MIT-lizenzierte Mehrsprachenmodell.

- **Der Name unter „Ansprechpartner" wurde nur halb entfernt.** Steht die
  Beschriftung allein auf einer Zeile und darunter „Nachname Vorname",
  blieb der Vorname stehen, sobald er zugleich ein gewöhnliches Wort ist –
  aus „Mayer Roman" wurde „[NAME_1] Roman". Solche Zeilen werden jetzt
  ganz genommen. Eine Abteilung an derselben Stelle („Technischer
  Innendienst") bleibt weiterhin unangetastet. Nebenbei behoben:
  „Ansprechpartner" zählte überhaupt nicht als Namensfeld, obwohl
  „Kontaktperson" es seit jeher tut.

- **Der Firmenname ohne Rechtsform blieb stehen, wenn ein Branchenwort
  dazwischenstand.** „Kranzbichler Handels GmbH" wurde entfernt, das
  nackte „Kranzbichler" drei Absätze später nicht – bei „Kranzbichler
  GmbH" dagegen schon. Jetzt greift beides. Gewöhnliche Wörter sind davon
  ausgenommen: „Deutsche Bank AG" macht kein „deutsche" im Text zur Firma.

- **Derselbe Wert hieß im selben Dokument einmal Name und einmal Ort.**
  „Anna Musterfrau … Musterfrau" ergab „[NAME_1]" und „[ORT_1]“ – an der
  zweiten Stelle fehlt der Vorname, und ohne ihn wurde daraus ein Ort.
  Entfernt war beides, aber es las sich wie zwei verschiedene Dinge. Ein
  Wert behält jetzt die Bezeichnung seines ersten Vorkommens.

- **Datumsangaben wurden nicht mehr entfernt.** Ein Datum ganz aus Ziffern
  („01.03.2026") fiel seit der letzten Fassung durch eine Prüfung, die für
  Namen gedacht war, und blieb im Dokument stehen – auch in der Betriebsart
  „verschieben", und ohne Zeile im Prüfbericht. Betroffen war nur, wer
  Datumsangaben ausdrücklich eingeschaltet hatte.

- **Länder und Kontinente werden nicht mehr geschwärzt.** „Die Lieferung geht
  in die Vereinigten Staaten", „Marktschwäche in Asien", „die Norm gilt in
  Rumänien" – solche Angaben sagen nichts über eine Person und bleiben
  jetzt stehen. Gehört der Ländername dagegen zu einer Anschrift oder steht
  er hinter einer Beschriftung wie „Wohnsitz" oder „Geburtsort", wird er
  weiterhin entfernt. **Städte sind nicht betroffen** – „Ich bin gerade in
  Bilbao" bleibt eine Angabe über eine Person und wird weiter geschwärzt.

- **Abgekürzte Wörter wurden zu Webadressen.** Steht im Text „bzw. deutsche"
  oder „incl. der", liefert manche PDF den Punkt ohne Leerzeichen – daraus
  wurde „bzw.de" beziehungsweise „incl.de", eine gültige Adresse mit
  Länderendung, und sie wurde entfernt. Solche Wortpaare bleiben jetzt
  stehen. Echte Adressen sind nicht betroffen, auch nicht ohne „www." davor.

- **Zahlenspalten aus Bilanzen wurden als Telefonnummern geschwärzt.** In
  Geschäftsberichten und Preistabellen stehen Vorjahr und laufendes Jahr
  nebeneinander – „64.518  65.133". Das galt als eine Rufnummer und wurde
  entfernt, ebenso Zahlenbereiche wie „12200-23200" und ein Datum mit
  folgender Zahl. Solche Zahlen bleiben jetzt stehen. Umgekehrt wird eine
  echte Rufnummer sicherer erkannt: Die Beschriftungen „Telefon", „Fax",
  „Mobil", „Durchwahl" und ihre Entsprechungen in den anderen
  Oberflächensprachen zählen jetzt mit – bisher erkannte das Programm dort
  nur die englischen Wörter.

- **Namen in einer nummerierten Tabelle blieben stehen.** Eine
  Teilnehmerliste oder Personaltabelle in der üblichen Form – Spaltenkopf,
  darunter „1.1 Auersperg Bernhard Montage 03.03.2026" – wurde gar nicht
  bereinigt: Solche Zeilen sahen aus wie die Positionsliste eines Angebots,
  in der Sachbegriffe stehen bleiben sollen. Trägt der Spaltenkopf eine
  Personenbeschriftung („Name", „Nachname", „Surname" …), gelten die Zeilen
  darunter jetzt als Namen. Positionslisten bleiben unverändert
  verschont – auch dann, wenn im Briefkopf „Sachbearbeiter:" steht.

- **Aus einem Namen wurden manchmal zwei Platzhalter nebeneinander.** Wenn ein
  Nachname auch allein im Dokument stand, ersetzte die Nachbearbeitung an einer
  Stelle wie „Anna Musterfrau GmbH" erst den Nachnamen und dann den Vornamen –
  im Ergebnis sah das aus wie zwei verschiedene Personen. Jetzt gewinnt der
  längste bekannte Name.

- **Erfundene Werte standen in keiner Zuordnung.** Wer „Werte erfinden“
  gewählt hatte, bekam ein Ergebnis, in dem „Anna Musterfrau“ zu „Greta
  Mayrhofer“ geworden war – in der Zuordnung stand davon nichts, sobald im
  selben Dokument auch nur eine anonyme Ersetzung vorkam. Damit ließ sich
  kein erfundener Wert zurückholen, und die Zuordnungsdatei verschwieg die
  Ersetzung. Am heikelsten war das Dritte: Wer das Ergebnis liest, sieht
  einen glaubhaften Namen und hat keinen Anhaltspunkt, dass er erfunden
  ist. Jetzt steht jede Ersetzung in der Zuordnung.

- **Die Zuordnung nannte Geschwärztes „ersetzt“.** Eine E-Mail teilt sich
  eine Zuordnung mit ihren Anhängen, und der Anhang darf geschwärzt werden,
  während der Mailtext einen Platzhalter trägt. In der Zuordnung stand
  dann für alle drei Stellen dasselbe – „ersetzt“ –, und das
  Zurückholen suchte im Anhang einen Platzhalter, den es dort nicht gibt:
  Der Balken blieb liegen. Jetzt steht je Fundstelle, was dort wirklich
  geschah, und beide Anhänge kommen zurück.

- **Werte, die nur in einem Bild standen, ließen sich nicht zurückholen.**
  Im Trefferpanel standen sie doppelt – einmal als Platzhalter, den es im
  Dokument nirgends gab („Der Platzhalter wurde im Dokument nicht
  gefunden“), einmal als geschwärzte Stelle. Die erste Zeile war reine
  Buchführung und ist verschwunden.

- **Geschwärzte Werte ließen sich nur einmal zurückholen.** Steht derselbe
  Wert an mehreren Stellen, holt ein Klick alle zurück – die übrigen Zeilen
  blieben aber im Trefferpanel stehen, und der nächste Klick darauf meldete
  „Nicht eindeutig“. Sie verschwinden jetzt mit.

- **Rücknahmen fehlten im Prüfprotokoll, wenn der Lernmodus aus war.** Wer
  einen zurückgeholten Wert im Nachbessern-Fenster wiederherstellte, fand
  den Vorgang nicht im Prüfprotokoll wieder, sobald die Lernfragen
  abgeschaltet waren – der Nachweis hing an einem Schalter, der nur die
  Regelvorschläge meint. Bei eingeschaltetem Prüfprotokoll wird jetzt
  unabhängig davon nach dem Grund gefragt und die Zeile geschrieben.

- **Hineingezogene Dateien blieben unbereinigt – und wurden nicht einmal
  gemeldet.** Wer eine Datei in ein Dokument zieht, statt sie als Anhang zu
  verschicken, legt Word oder PowerPoint sie vollständig im Dokument ab.
  Sie stand danach unverändert im Ergebnis, samt ihrem ursprünglichen
  Dateinamen und Ablagepfad – und die tragen in der Praxis oft selbst einen
  Namen. Solche Dateien werden jetzt wie das übrige Dokument bereinigt.

- **Und wo das nicht geht, sagt Maskuro es.** Steckt in einem eingebetteten
  Objekt ein altes Format (Word 97, Excel 97), für das es keine Bereinigung
  gibt, erscheint jetzt eine ACHTUNG-Meldung mit dem Namen der Datei.
  Bisher wurde sie stillschweigend unverändert weitergegeben.

- **Zerrissene Wörter und Kürzel wurden für Namen gehalten.** Wenn ein Wort
  in einer PDF am Zeilenende getrennt ist, kommt beim Auslesen mancher
  Dateien ein Bruchstück heraus – „Jahresent… gelts", „Gewerbli…". Solche
  Bruchstücke, zusammengeklebte Wörter („TürverschlussmitV") und nackte
  Kürzel („JY", „FFB") wurden geschwärzt, als wären sie Namen. Sie bleiben
  jetzt stehen. Ein Name mit demselben Trennungsschaden bleibt weiterhin
  geschwärzt, solange eine Anrede dabei ist – und Namen, die von Haus aus
  einen Großbuchstaben im Wort tragen (McKenzie, MacDonald, LeBlanc), sind
  davon ohnehin nicht betroffen.

- **Maßangaben und Monate galten als Anschrift.** In technischen
  Unterlagen wurden „2000 Lux", „1200 Mbit", „1500 Watt", „5308 Platz" und
  „2022 Mrz" geschwärzt – vier Ziffern und ein großgeschriebenes Wort sahen
  aus wie eine Postleitzahl mit Ort. Eine Postleitzahl zählt jetzt nur noch,
  wenn auch ein Anschriftsignal dabei ist: eine Länderkennung, eine
  Feldbeschriftung, der Zeilenanfang, eine Straße in der Zeile darüber oder
  ein Ort, den auch die Spracherkennung dort sieht. In fünf
  Leistungsverzeichnissen verschwinden damit 14 falsche Schwärzungen, ohne
  dass eine echte Anschrift stehen bleibt.

- **Die genauere Erkennung ersetzte zu viel.** Die zuschaltbare Stufe
  „genauere Erkennung" hat in deutschen Geschäftsunterlagen Sachbegriffe
  für Namen und Orte gehalten – „Photovoltaikanlage", „Einspeisepunkt",
  „Flachdach", „Personaleingang" – und Firmenbezeichnungen aus laufenden
  Positionslisten geschwärzt. Grund war eine Schonung: Ihre Treffer wurden
  von den Prüfungen ausgenommen, die eine Positions- oder
  Verzeichniszeile erkennen. Diese Schonung gilt jetzt nur noch für
  mehrteilige Namen, für die es die Stufe gibt – „Anna Huber" in einer
  Verzeichniszeile bleibt also erkannt, ein einzelnes Sachwort in einer
  Positionszeile fällt weg. In einer technischen Ausschreibung halbiert
  das die falschen Schwärzungen der Stufe, ohne dass ein Name verloren
  geht.

- **Diagramme brachten ihre vollständigen Quelldaten mit – ungeprüft.** Wer
  in Word oder PowerPoint ein Schaubild einfügt, legt das Programm die
  Tabelle, aus der es gerechnet wurde, als eigene Datei in das Dokument.
  Sichtbar sind davon nur die paar Zahlen im Schaubild; in der Tabelle steht
  die ganze Liste, samt der Zeilen, die im Schaubild gar nicht vorkommen.
  Diese Tabelle wurde bisher unverändert weitergegeben. Sie wird jetzt
  mitbereinigt, mit denselben Platzhaltern wie das übrige Dokument.

- **Dasselbe für eingebettete Objekte in OpenDocument-Dateien** (ODT, ODS,
  ODP): Ein eingefügtes Schaubild oder eine eingefügte Tabelle blieb
  unangetastet.

- **Word-Dokumente: Fußnoten und Endnoten wurden nicht bereinigt.** Ihr Text
  blieb vollständig im Ergebnis stehen – auch Namen, Anschriften und
  Kontonummern. Betroffen war jedes Word-Dokument mit einer Fuß- oder
  Endnote. Ebenso blieb ein Autotext-Baustein unberührt, der unsichtbar mit
  dem Dokument mitreist.

- **Word: Angaben in Auswahllisten, Kommentaren und Bildbeschreibungen.**
  Die Einträge eines Auswahlfelds (sichtbar erst beim Aufklappen), der
  Verfasser eines Kommentars, die Beschreibung einer Zeichnung und die
  Adresse hinter einem Verweisbefehl standen weiter im Ergebnis.

- **Excel: Die Pivot-Tabelle trug die Ausgangsdaten ein zweites Mal.** Eine
  Mappe mit einer Pivot-Tabelle bewahrt darin eine vollständige Kopie der
  ausgewerteten Zeilen auf – unsichtbar, aber in der Datei. Diese Kopie blieb
  bisher unverändert stehen, auch wenn im Blatt selbst alles ersetzt war.
  Betroffen war jede Auswertung, die mit einer Pivot-Tabelle weitergegeben
  wurde.

- **Excel: Unterhaltungskommentare und ihre Verfasser.** Der Text eines
  Kommentars der neueren Bauart und das Verzeichnis der Kommentierenden –
  Anzeigename und Anmeldekennung, in Firmen meist die E-Mail-Adresse –
  standen weiter im Ergebnis. Dasselbe Verzeichnis in Word-Dokumenten
  ebenfalls.

- **Selbstdefinierte Dokumenteigenschaften in Word und Excel.** Felder wie
  „Mandant" oder „Aktenzeichen", die eine Kanzlei ihren Vorlagen mitgibt,
  wurden bisher nicht bereinigt. Sie sind in keiner Ansicht zu sehen und
  wandern trotzdem mit jeder Kopie mit.

- **Tabellen (ODS): die Auswahlliste einer Zelle.** Wie in Excel seit der
  vorigen Fassung wird jetzt auch in OpenDocument-Tabellen bereinigt, was
  beim Aufklappen einer Zelle erscheint. Bezüge auf andere Zellen bleiben
  dabei unangetastet, damit die Liste weiter funktioniert.

Alle diese Stellen lassen sich wie gewohnt über die Zuordnung wieder
zurückholen.

- **Outlook-Nachrichten: eine beschädigte Datei beendete die Bereinigung
  hart.** Bestimmte kaputte `.msg`-Dateien führten zu einem Abbruch statt zu
  einer Meldung; jetzt werden sie gelesen, soweit sie lesbar sind.

- **Die Zuordnungsdatei ist jetzt nur für Sie lesbar.** Sie enthält die
  Originaldaten im Klartext und lag bisher mit den üblichen Rechten neben dem
  Ergebnis – auf einer gemeinsamen Ablage konnte sie damit jeder öffnen. Am
  bereinigten Ergebnis selbst ändert sich nichts; es soll ja weitergegeben
  werden.

- **Nachgeladene Sprachmodelle werden vor dem Auspacken genauer geprüft.**
  Ein manipuliertes Paket – etwa aus einer Firmenfreigabe, aus der mehrere
  Arbeitsplätze bedient werden – konnte beim Entpacken Dateien außerhalb des
  vorgesehenen Ordners ablegen. Am gewöhnlichen Nachladen ändert sich nichts.

- **Bildschirmfoto aufnehmen – und es wird gleich bereinigt.** Mit
  `Strg+Umschalt+B`, über „Datei → Bildschirmfoto aufnehmen …“ oder über das
  Symbol in der Taskleiste ziehen Sie einen Rahmen über den Bildschirm. Was
  darin liegt, geht anschließend denselben Weg wie jede andere Datei: Die
  Texterkennung liest den Bildschirmtext, Namen, Anschriften, Rufnummern und
  E-Mail-Adressen werden geschwärzt, und danach steht das Bild im Editor
  offen, wo Sie mit einem Rahmen nachschwärzen können, was übersehen wurde.
  Das bereinigte Bild landet auf dem Schreibtisch (oder in Ihrem
  eingestellten Ausgabeordner); die **rohe** Aufnahme wird nirgends
  abgelegt und beim Beenden gelöscht. Die Texterkennung wird für diesen
  Lauf eingeschaltet, auch wenn sie sonst aus ist – an einem Bild wäre ohne
  sie nichts zu finden. Auf dem Mac fragt das System beim ersten Mal nach
  der Freigabe „Bildschirmaufzeichnung“.

- **Auf Bilder lässt sich jetzt zeichnen: Rechteck, Ellipse, Pfeil, Text und
  nummerierte Schrittmarken.** In sechs Farben und drei Strichstärken, mit
  den Tasten 1 bis 5 zu wählen. Gedacht ist das für Bildschirmfotos und
  Anleitungen: zeigen, worauf es ankommt, ohne dafür ein zweites Programm zu
  öffnen. Rückgängig und das Nachziehen an den Griffen gelten wie für jeden
  Balken – eine Anmerkung lässt sich also verschieben und aufziehen,
  nachdem sie gesetzt ist.
  **Zeichnen ist ausdrücklich kein Schwärzen.** Ein gezeichnetes Rechteck
  ist ein Rahmen, kein Balken: Was darunter steht, bleibt lesbar und geht
  mit der Datei hinaus. Zum Entfernen von Angaben sind weiterhin
  „Schwärzen“ und „Verpixeln“ da; die Zeichenwerkzeuge stehen deshalb in
  einer eigenen Zeile der Werkzeugleiste, und die Hinweiszeile sagt es,
  solange eines von ihnen gewählt ist.

- **Das bearbeitete Bild geht mit einem Klick in die Zwischenablage.**
  „Bild kopieren“ im Editor (oder `Strg+C`) legt es so ab, wie es dasteht –
  einfügen genügt, um es in eine Nachricht oder Mail zu bringen. Damit ist
  der Weg vom Tastendruck bis in den Chat vier Schritte lang und braucht
  keinen Ordner.

- **Dazu ein Textmarker, Schatten und Verläufe.** „Hervorheben“ färbt eine
  Fläche ein, ohne sie zu verdecken – der Inhalt darunter bleibt lesbar,
  und genau daran unterscheidet er sich vom Balken. „Schatten“ hebt eine
  Anmerkung von unruhigem Untergrund ab, „Verlauf“ lässt die Farbe in
  Zugrichtung auslaufen; beides gilt für alle sechs Zeichenwerkzeuge.

- **Behoben, bevor es jemanden traf:** Die neue Werkzeugzeile wäre bei
  jedem, der Maskuro schon benutzt hat, fast leer erschienen – die
  gemerkte Fensteraufteilung stammte aus der Zeit davor und hätte ihr
  keinen Platz gelassen. Eine veraltete Aufteilung wird jetzt verworfen;
  das Editorfenster steht dann einmalig in seiner Grundaufteilung da.

- **Das eigene Bildschirmfoto lässt sich abschalten.** Wer Greenshot, ShareX
  oder das Ausschneidewerkzeug gewohnt ist, schaltet unter „Einstellungen →
  Programm“ „Bildschirmfoto mit Maskuro aufnehmen“ aus. Maskuro meldet das
  Tastenkürzel dann gar nicht erst an – es bleibt Ihrem Werkzeug –, und die
  Umstellung gilt sofort, ohne Neustart. Bereinigen lässt sich ein so
  aufgenommenes Bild weiterhin: Strg+V holt es aus der Zwischenablage ins
  Fenster.

---

## 0.10.37-alpha.20260821 – 21. August 2026

### Neu

- **Beim Anonymisieren trägt jetzt jede Fundstelle ihre eigene Nummer.**
  Bisher hießen alle Personen `[NAME]`, alle Orte `[ORT]` – dadurch ließ sich
  nicht mehr sagen, welche Stelle zu welchem Wert gehörte, und es gab nichts
  zurückzuholen. Jetzt zählen die Nummern je Vorkommen weiter: Derselbe Name
  steht an drei Stellen als `[NAME_1]`, `[NAME_3]` und `[NAME_7]`. Im Dokument
  ist damit weiterhin nicht zu erkennen, welche Stellen zusammengehören – mit
  der Zuordnungsdatei lässt sich aber jede einzelne zurückholen. Die
  Zuordnungsdatei ist deshalb auch beim Anonymisieren wieder wählbar; bewahren
  Sie sie getrennt vom Ergebnis auf.
- **Monate, Wochentage, Währungen, Einheiten und Firmen-Rechtsformen in
  allen 48 Dokumentsprachen gelten nicht mehr als Namen oder Orte.** Die
  Kalender- und Einheitennamen kommen aus Unicode CLDR (erzeugt, nicht
  geschrieben), die Rechtsformen aus dem Gesellschaftsrecht der Länder –
  auch mehrwortig („sp. z o.o.", „Pty Ltd") und vorangestellt („株式会社").
  Wo ein Monatsname zugleich ein Vorname ist (Juli, August, May), entscheidet
  die Bauform: mit Tag oder Jahr daneben ein Datum, sonst ein Name. Dazu
  Anreden und Titel, ganze Grußformeln, Dokumentarten und Straßen-Grundwörter
  für 28 Sprachen mit eigenem Sprachmodell, Gesetzeskürzel (DSGVO, UStG,
  ABGB, § 6 Abs 1 Z 27 UStG) sowie Sprachnamen als Feldwert („Sprache:
  Deutsch“). Die Listen stehen unter „Hilfe → Wortlisten …".
- **Indien: Anschrift und PIN-Code werden erkannt** – „15 गांधी मार्ग",
  „नई दिल्ली 110001" ebenso wie „15 Gandhi Marg, New Delhi 110001". Das
  Länderpaket Indien kannte bisher nur Kennnummern; in Hindi-Dokumenten
  blieben Anschriften deshalb stehen.
- **Jede bereinigte Office-Datei wird vor der Übergabe noch einmal als Paket
  geöffnet.** Ein Textauszug merkt nicht, wenn Word, Excel oder LibreOffice
  die Datei verweigern würden (doppelter Eintrag, abgerissenes XML, ein
  fehlender Teil). Und gezählt wird gegen das Original, was eine
  Bereinigung nie ändern darf: Seiten einer PDF, Blätter, Zeilen und Zellen
  einer Tabelle, Folien einer Präsentation. Schlägt die Probe an, steht eine
  ACHTUNG-Warnung im Ergebnis und im Prüfbericht – das Original bleibt
  unverändert.
- **Auch die Automatik schwärzt das ganze Feld.** Im Schwärzmodus deckt
  der Balken in kurzen Zeilen – Adressblock, Tabellenzelle, Kopfdaten –
  die ganze Zeile statt nur den gefundenen Wert: Ein Balken in Wortlänge
  verrät, wie lang das Wort war. Beschriftung und Beträge daneben bleiben
  stehen, und Fließtextzeilen (länger als die halbe Textbreite) werden
  weiter wortgenau geschwärzt, damit ein Name mitten im Satz nicht den
  ganzen Satz schwarz macht.
- **Zurückgeholtes sieht wieder aus wie im Original.** „Original
  zurückholen" und „Ersetzung zurücknehmen" im PDF-Editor schreiben den
  Bereich jetzt exakt aus der Quelldatei zurück – dieselbe Schrift,
  dieselbe Größe, dieselbe Farbe und Lage, auf einem Scan dieselben
  Bildpunkte. Bis dahin wurde der Text in einer Ersatzschrift neu
  eingelegt und sah erkennbar nachgebaut aus. Der Balken einer früheren
  Schwärzung verschwindet dabei ganz, statt weiß übermalt zu werden – ein
  farbiger Zellgrund in einer Tabelle bleibt erhalten. Das gilt auch auf
  gedrehten Seiten, für Text aus eingebundenen Formular-Objekten und für
  **ausgefüllte Formularfelder**: Auf der dafür gerasterten Arbeitskopie
  kommt der Ausschnitt aus der neu gerenderten Originalseite zurück – auch
  dort, wo keine Textschicht den Feldwert kennt. Auch **ersetzte Bilder**
  im PDF kommen so zurück – verpixelt, verwischt oder ganz entfernt, ganz
  oder nur der gezogene Ausschnitt. Nur wo die Quelldatei nicht mehr neben
  dem Ergebnis liegt, bleibt es beim bisherigen Weg.
- **Geschwärzte und ersatzlos entfernte Werte lassen sich auch in Word,
  Excel, PowerPoint und OpenDocument zurückholen.** Bisher brauchte die
  Rücknahme dort einen Platzhalter im Text – ein Balken oder eine Lücke
  hatte keinen Rückweg. Jetzt bietet das Trefferpanel die Zeilen
  „geschwärzt" und „entfernt" an, sobald die unangetastete Quelldatei
  neben dem Ergebnis liegt: Maskuro vergleicht das Ergebnis mit dem
  Original und setzt den Wert an der Stelle des Balkens oder der Lücke
  wieder ein – samt Formatierung, ein zerteilter Lauf wird wieder ganz.
  Gilt ebenso für Text, HTML, E-Mail und die Office-Anhänge einer E-Mail;
  trägt der Mailtext einen Platzhalter und der Anhang einen Balken, werden
  beide in einem Zug zurückgeholt.
- **Auch PDF-Anhänge einer E-Mail oder Outlook-Nachricht lassen sich
  zurückholen** – Platzhalter (nummeriert und anonym), Balken und
  ersatzlos Entferntes. Ohne Leinwand kommt die Stelle aus dem
  Originalanhang; zurück kommt der Wert glyphengenau, in der
  Lesereihenfolge des Originals.
- **Maskierte Werte lassen sich zurückholen** – im PDF und in der
  Textansicht. Eine Maske („**** **** **** **** 3201") ist nie eindeutig,
  zwei Nummern tragen dieselbe; deshalb nimmt die Rücknahme nie den
  wörtlichen Weg, sondern fragt das Original, welcher Wert an dieser
  Stelle stand. Bisher waren diese Zeilen im Trefferpanel gar nicht
  bedienbar.
- **Eingebettete Bilder in Word, Excel, PowerPoint und OpenDocument lassen
  sich zurückholen.** Ein im Bild geschwärzter Wert kommt über seine
  Panelzeile zurück – Maskuro liest das Originalbild und holt genau diese
  Stelle; ein verwischtes, entferntes oder mit Gesichtern und Codes
  bearbeitetes Bild holt der neue Eintrag „Eingebettete Bilder
  zurückholen" im Menü Bearbeiten als Ganzes aus der Quelldatei – auch
  durch die Office-Anhänge einer E-Mail oder Outlook-Nachricht hindurch.
  Ein Bild, das selbst als Anhang hängt und per Texterkennung geschwärzt
  wurde, kommt ebenso über seine Panelzeile zurück.
- **Erfundene Werte lassen sich in der Textansicht zurückholen.** Bisher
  meldete das Panel dort „Nicht eindeutig". Jetzt sucht die Rücknahme den
  Wert im Original und verlangt an derselben Stelle im Ergebnis genau den
  erfundenen Ersatz – ein erfundener Name wird nie wörtlich überall
  ersetzt, er könnte irgendwo echt stehen.
- **Rücknahme in Word, Excel, PowerPoint und OpenDocument behält die
  Formatierung des Originals.** Stand ein Wert über mehrere Läufe – „Anna"
  normal, „Musterfrau" fett und rot –, kam er bisher ganz in den ersten
  Lauf zurück und verlor Fett und Farbe. Jetzt verteilen sich die Zeichen
  wieder wie im Original; ein Word-Absatz ist danach Byte für Byte der
  ursprüngliche. Dasselbe gilt für HTML-Seiten, den HTML-Teil einer
  E-Mail und den HTML-Körper einer Outlook-Nachricht (.msg) – bei der
  E-Mail bleibt außerdem der Doctype erhalten, den die Bereinigung bisher
  stillschweigend entfernte.
- **Textdateien behalten ihre Kodierung.** Bereinigung und Zurückholen
  schreiben `.txt`, `.md` und `.csv` jetzt in der Kodierung, in der sie
  geliefert wurden – UTF-8 mit und ohne BOM, UTF-16, Windows-1252. Bisher
  wurde eine Windows-1252-Datei stets zu UTF-8, und eine UTF-16-Datei kam
  beschädigt zurück, auch wenn darin nichts zu ersetzen war.
- **Zurückgeholte Bilder behalten ihren Farbmodus.** Ein Graustufenscan
  kommt als Graustufen zurück statt als dreimal so große RGB-Datei, eine
  Palette als Palette, Schwarzweiß als Schwarzweiß – beim ganzen Bild mit
  denselben Werten wie im Original. Gilt für Bilddateien und für Bilder in
  PDFs. CMYK und 16 Bit bleiben RGB, weil das PNG-Ergebnis beides nicht
  tragen kann.
- **Ein Rahmen im Bild holt die ganze Bearbeitung zurück, die er berührt.**
  Verpixelte Gesichter tragen einen Rand um die erkannte Box; wer den
  Rahmen nur über das Gesicht zog, behielt einen verpixelten Ring. Jetzt
  wächst der Rahmen auf die zusammenhängende Veränderung gegenüber dem
  Original – ein Rahmen über der Augenpartie genügt. Getrennte Balken
  daneben bleiben stehen; bei einem ganz entfernten oder ganz verwischten
  Foto gilt weiter der gezogene Rahmen. Gilt für Bilddateien und Bilder in
  PDFs.
- **Schwärzbalken über die ganze Zeile.** Im Zeilenmodus des Editors läuft
  der Balken jetzt vom ersten bis zum letzten Wort der Zeile, nicht mehr nur
  über das getroffene Wort – ein Balken in Wortlänge verrät, wie lang das
  Wort war, und aus sechs Zeichen vor einer Postleitzahl lässt sich ein
  Ortsname erraten. Beschriftungen, Beträge und Tabellenspalten neben dem
  Wert bleiben stehen – der Balken deckt das Feld, nicht die Zeile der
  Rechnung. Der neue
  Schalter „Ganze Zeile" neben „Textzeilen" stellt wieder auf wortgenau um,
  wenn die Nachbarwörter stehen bleiben sollen; die Wahl wird gemerkt.

### Behoben

- **Bilder in HTML-Seiten und E-Mails blieben ungeprüft – der Name im Logo
  stand nach der Bereinigung noch lesbar da.** Ein in die Seite eingebettetes
  Bild (``data:``-Adresse) wurde gar nicht angefasst, nur sein Alternativtext;
  das Logo am HTML-Zweig einer Mail (Inline-Bild ohne Dateinamen) fiel durch
  den Anhangsfilter; und beim benannten Bild-Anhang blieb die Bildregel
  „verwischen“/„entfernen“ ohne Wirkung. Jetzt laufen alle drei denselben
  Weg wie eine Bilddatei: Texterkennung im behaltenen Bild, Gesichter, Codes,
  Metadaten und die Bildregel. Der Bericht nennt die Bilder – auch die
  Warnung, wenn sie ohne Texterkennung ungeprüft bleiben –, und
  „Eingebettete Bilder zurückholen“ sowie die Rücknahme aus dem Trefferpanel
  kennen diese Bilder ebenfalls.
- **Eine Office-Datei mit Bild ließ sich gar nicht bereinigen, wenn die
  Texterkennung die Sprache nicht beherrscht.** Auf dem Mac liest die
  systemeigene Texterkennung; für Hindi, Griechisch, Kroatisch oder
  Litauisch kann sie das nicht und sagt es seit Kurzem auch – bei Word,
  Excel, PowerPoint und OpenDocument brach darüber aber die **ganze**
  Bereinigung ab, und es entstand keine Datei. Dabei ließ sich der Text
  einwandfrei bereinigen; nur das Bild war nicht lesbar. Jetzt wird die
  Datei geschrieben wie bei PDF und einzelnen Bildern, und im Ergebnis
  steht, dass die Bilder NICHT geprüft wurden – mit dem Grund und dem
  Hinweis auf „Sprachen verwalten“.

- **In Excel-Mappen blieben Namen in Auswahllisten stehen.** Die Liste
  eines Dropdown-Felds (Datenüberprüfung) wird jetzt wie jeder andere
  Zellinhalt bereinigt; Bezüge auf Zellbereiche bleiben unangetastet,
  damit die Mappe heil bleibt.
- **Wo der Platzhalter nicht hinpasste, stand ein schwarzer Balken – jetzt
  steht dort eine kürzere Schreibweise.** `[GEBU_1]` statt `[GEBURTSDATUM_1]`,
  und erst wenn auch die kürzeste Form nicht mehr passt, wird geschwärzt. Ein
  Balken sagt niemandem mehr, dass dort etwas stand; ein kurzer Platzhalter
  sagt es. Der Nachbessern-Editor konnte das schon, die selbsttätige
  Bereinigung bisher nicht. Die Zuordnungsdatei führt beide Schreibweisen auf
  denselben Wert, damit sich auch das Gekürzte zurückholen lässt.
- **Der erste Klick auf „Ersetzen" ließ das Nachbessern-Fenster kurz stehen.**
  Die Erkennung, die dem Platzhalter seine Art gibt (`[NAME_3]` statt
  `[BEGRIFF_3]`), wurde erst in diesem Moment geladen – rund zwei bis drei
  Sekunden. Sie wird jetzt beim Öffnen des Fensters im Hintergrund
  vorbereitet; gemessen sind aus 2289 Millisekunden 193 geworden.
- **Zwei gleichzeitige Bereinigungen konnten dasselbe Sprachmodell doppelt
  laden** – etwa die Ordnerüberwachung und das Hauptfenster. Weil jedes
  Modell mehrere hundert Megabyte belegt, stand der Speicherbedarf dabei
  kurzzeitig beim Doppelten. Jetzt wartet der zweite Lauf auf das Modell des
  ersten.
- **Der Ort in der Datumszeile wird jetzt auch dann entfernt, wenn das
  Sprachmodell ihn allein nicht erkennt:** Was als Postleitzahl mit Ort
  sicher gefunden ist („3335 Amstetten"), zieht seinen Ortsnamen im ganzen
  Dokument nach – wie ein Nachname aus einem Vollnamen. Und ein Kürzel
  mit Ziffer vor einem Namen („T3 Hofbauer Christian") bleibt lesbar,
  statt mit im Platzhalter zu verschwinden.
- **Drei Lecks aus der Zweitlesung eines echten Auftrags geschlossen:** Der
  Sachbearbeiter „T3 Hofbauer Christian" galt wegen des Kürzels „T3" als
  Spaltenkopf und blieb lesbar; ein Ort, den das Sprachmodell über den
  Zeilenumbruch in den Spaltenkopf hinein las, verschluckte „Pos." und
  ließ den Kunden-Vornamen stehen; und ein Name samt Anrede („Herr Robert
  Köttel") zog nur den Nachnamen nach, nicht den Vornamen – und dafür
  jedes „Herr". Kürzel sind jetzt reine Buchstaben, Zweiwortnamen keine
  Kopfzeile, Treffer werden vor einem Spaltenkopf abgeschnitten, und die
  Anrede zählt nicht zum Namen.
- **Der Ort in der Datumszeile („Melk, 05.08.2026") direkt unter dem
  Anschriftenblock blieb lesbar.** Das Sprachmodell klebte ihn mit dem
  Ort der Postleitzahl-Zeile zu einem Treffer, und der fiel als Ganzes
  gegen das Postleitzahl-Muster. Jetzt bleibt der herausragende Rest ein
  eigener Treffer. Gefunden durch die neue Zweitlesung des Ergebnisses
  (`werkzeuge/zweitlesung.py`).
- **Mac: Ein Scan in einer Sprache, die die systemeigene Texterkennung nicht
  beherrscht (etwa Hindi, Griechisch, Kroatisch, Litauisch), galt als
  geprüft.** Gelesen wurde mit dem englischen Rückfall, die fremde Schrift
  blieb im Bild, und der Bericht sagte „nichts gefunden". Jetzt heißt es
  „Bild(er) wurden NICHT geprüft" mit dem Grund, und die Sprachenverwaltung
  verspricht für solche Sprachen keine Texterkennung mehr, nur weil eine
  Tesseract-Sprachdatei daliegt.
- **Im PDF bleibt das Satzzeichen hinter einem ersetzten Wert stehen.** Aus
  „Aufnahme am 01.03.2026, Entlassung am 04.03.2026." wurde bisher
  „Aufnahme am [DATUM_1] Entlassung am [DATUM_2]" – Komma und Schlusspunkt
  fehlten, bei Platzhaltern ebenso wie bei verschobenen Daten. Entfernt
  wird jetzt nur der erkannte Wert, nicht das ganze Wort bis zum nächsten
  Leerzeichen; Komma, Semikolon, Punkt oder Klammer dahinter bleiben an
  ihrer Stelle, und der Platzhalter läuft nicht über sie hinweg.
- **Russisch und Ukrainisch liefen unbemerkt mit dem schwächeren
  Mehrsprachenmodell**, wenn ein Hilfspaket für die Wortformenanalyse
  (`pymorphy3`) fehlte – die eigenen Modelle ließen sich dann nicht laden,
  und „Львів" wurde zur Person. Für die Erkennung von Namen ist die
  Wortformenanalyse nicht nötig; das Modell wird jetzt ohne sie geladen, und
  Orte sind wieder Orte.
- **Die Lizenzhinweise in 16 Sprachen waren auf altem Stand.** Dort stand
  noch, der MPL-Quellcode werde „auf Anfrage" bereitgestellt, QPDF galt als
  MPL-2.0, sieben Bausteine fehlten in der Tabelle (wordfreq, Qt, ONNX
  Runtime, tokenizers, zxing-cpp, llama.cpp, YuNet), der spaCy-Absatz war
  englisch, und am Ende hing ein englischer Ersatzabschnitt. Jetzt stehen
  alle 18 Fassungen auf dem Stand der deutschen: Quellarchive dauerhaft
  unter maskuro.com/quellcode/oss/, QPDF Apache-2.0, Qt-LGPL-Weg,
  Modellherkunft. Auch die englische Tabelle hat die fehlenden Zeilen.

- **Vertragswörter im Genitiv („des Angebotsinhaltes", „des Anbotes",
  „des Terminplanes") gelten nicht mehr als Ort.** Ein einzelnes Wort
  hinter einem Genitiv- oder Dativartikel mit Flexionsendung ist ein
  Gattungswort – Ortsnamen flektieren nicht („nach Graz"). Steht der Ort
  anderswo im Dokument ohne Artikel („Burgenland"), bleibt auch „des
  Burgenlandes" erkannt.
- **Verschobene, maskierte und erfundene Werte rasterten die PDF-Seite.**
  Die Nachprüfung nach dem Entfernen erlaubte im Fundrechteck nur einen
  Platzhalter in eckigen Klammern; ein verschobenes Datum („01.07.2026")
  oder ein maskierter Wert („****1234") galt als übersehener Rest, und die
  Seite wurde sicherheitshalber in ein Bild umgewandelt – bei „Ersetzen"
  nicht. Jetzt bleiben solche Seiten Text, und das Zurückholen aus Panel
  oder Rahmen liefert wieder das Original.
- **Mehrwortige Ersatzwerte ließen sich im PDF nicht über das Trefferpanel
  zurücknehmen.** Ein erfundener Name („Greta Mayrhofer") oder eine
  maskierte IBAN („**** **** **** **** 3201") besteht aus mehreren Wörtern;
  die Fundstellensuche verglich Wort für Wort und meldete „Der Platzhalter
  wurde im Dokument nicht gefunden". Jetzt werden aufeinanderfolgende
  Wörter derselben Zeile zusammengelesen.
- **Nach dem Zurückholen eines ersatzlos entfernten Werts blieb seine
  Panelzeile stehen.** Werte, die die Strategie „schwärzen" im
  Platzhaltermodus ohne Ersatz entfernt, haben keinen Platzhalter, an dem
  das Panel ein Verschwinden messen konnte. Jetzt wird die Zeile
  gestrichen, sobald der Wert wieder im Dokument steht.

- **Abkürzungskomposita wie „E-Helfer" oder „U-Bahn" gelten nicht mehr
  als Name.**
- **Silbentrennungsreste („Leis-") und überlange Komposita
  („Bauarbeitenkoordinationsgesetzes", „Baustellenkoordinator") gelten
  nicht mehr als Name oder Ort.** In einem gescannten Ausschreibungstext
  wurden so 28 Wörter weniger geschwärzt.
- **Positionslisten gescannter Angebote gelten nicht mehr als
  Namensverzeichnis.** Der Zusatzdurchgang für Verzeichnisse (kurze
  Zeilen) machte aus „Kälterohr" und „Außengeräte" Personen; er setzt
  jetzt aus, sobald Positionsnummern wie „1.1.5" am Zeilenanfang stehen.
  Datumszeilen in Mailverläufen zählen dabei nicht als Positionsnummern.
- **Spaltenköpfe und Positionsnummern gescannter Angebote („Pos.",
  „Pos. 1.1.3", die Kürzel „E/L/S") galten als Name oder Ort.** Eine
  Abkürzung allein auf ihrer Zeile, eine Beschriftung samt Nummer und
  Einzelbuchstaben zeilenweise sind keine.
- **Die Seite „atmete" im Nachbessern-Fenster nach dem Öffnen der
  Vergleichslupe** – bei „Seitenbreite" und „Einpassen" hängt der Maßstab am
  Sichtfenster, und das ändert sich mit jedem Rollbalken, der kommt oder
  geht; jede folgende Aktion rückte die Seite ein Stück nach. Die Leinwand
  zieht das jetzt von selbst nach, bis es steht. Und Zoomknöpfe, Regler und
  Tastenkürzel halten die Bildmitte auch dann, wenn beim Hineinzoomen ein
  Rollbalken erscheint.
- **Quer gespeicherte Scans werden jetzt aufrecht gelesen, und
  Kleindruck in großen Scans geht nicht mehr verloren.** Ein 24-seitiges
  gescanntes Angebot behielt in jeder Fußzeile sechs Bank-IBANs,
  Firmenbuchnummer und UID lesbar: Der Scan lag im PDF um 90° gedreht,
  und die Texterkennung ließ bei sehr großen Bildern je nach Bildmaß
  ganze Zeilen aus. Jetzt wird die sichtbare Drehung berücksichtigt und
  große Bilder werden in überlappenden Bändern gelesen – die Fußzeilen
  sind schwarz.
- **Straßen nach Personen mit Bindestrich vor dem Grundwort („Josef
  Admanseder-Straße 7", „Abt-Karl-Straße 8", „Dr.-Karl-Renner-Straße 12")
  werden als Anschrift erkannt.** Im Briefkopf eines gescannten Angebots
  blieb eine solche Adresse lesbar, weil das Muster ein Leerzeichen vor
  „Straße" verlangte.
- **IBANs aus der Texterkennung, die ein O statt 0 oder ein l statt 1
  tragen, werden jetzt erkannt.** Im Kleindruck eines Scans liest die
  Texterkennung Ziffern gern als Buchstaben; die Nummer hatte dann die Form
  einer IBAN, aber die Prüfsumme ging nicht auf, und sie blieb stehen.
  Schlägt die Prüfsumme fehl, wird jetzt die Lesart mit Ziffern probiert –
  stimmt sie dann, ist es die IBAN. Falsche Prüfziffern bleiben falsch.
- **Satzstücke wie „folgenden Codes auf der" galten als Ort.** Ein Name
  oder Ort, der mit einem kleingeschriebenen Wort beginnt, ist keiner –
  außer bei Adelspartikeln („van Gogh", „de Vries").
- **Im Editor blieb neben dem Schwärzbalken der letzte Buchstabe stehen**
  („…6", „…t", „…g"), und der Balken hatte die Höhe des gezogenen Rahmens
  statt der Zeile. Ursache: Konnte der Editor die Seite nicht vermessen,
  hielt er jeden Rahmen für „kein Wort getroffen" und wendete ihn exakt an
  – ohne die Regel, dass ein halbes Wort nie stehen bleibt. Dasselbe
  passierte bei einzelnen Textbefehlen, die der Editor nicht verorten
  konnte. Jetzt zählt daneben immer der Wortkasten: Was der Rahmen
  wesentlich überlappt, fällt ganz.
- **Der letzte Buchstabe eines Wortes ragte über den Schwärzbalken hinaus.**
  Der Balken war nach der Vorschubbreite aus den Schriftmetriken bemessen;
  zeichnet die Schrift eine Glyphe breiter, stand deren Rest neben dem
  Balken. Der Kasten eines Zeichens nimmt jetzt auch die gezeichnete Glyphe
  auf.
- **Die Meldung zum Umwandeln einer Seite in ein Bild versprach zu viel.**
  „Die Darstellung bleibt gleich" stimmt nach dem Rastern nicht: Schrift und
  Grafik sind dann Bildpunkte, die Datei wird größer. Die Meldung sagt das
  jetzt – und nennt auch den zweiten Grund, aus dem gerastert wird (der
  Umbau hätte die Seite beschädigt).
- **Der Text hinter einem entfernten Wert rückte um bis zu einen Punkt nach
  links.** Beim Umbau einer Zeile wurde der Anfang an der Glyphenkante
  gemessen, die Fortsetzung am Stiftursprung – die Vorbreite des ersten
  Buchstabens blieb als Fehler stehen („C" 0,5 pt, „I" 1,0 pt). Jetzt
  rechnet der Umbau durchgehend mit dem Stiftursprung; der Nachsatz steht
  auf den Zehntelpunkt an seiner Stelle.
- **Österreichische UID mit Abständen („ATU 187 35901") und eine
  Firmenbuchnummer ohne „FN" unter ihrer Beschriftung („Firmenbuchnummer:
  30799v") werden erkannt.** Beides stand handschriftlich auf einem
  gescannten Ausschreibungsformular und blieb lesbar, obwohl die
  Texterkennung es richtig gelesen hatte.
- **Quer liegende PDF-Seiten wurden nach dem Schwärzen grundlos in ein Bild
  umgewandelt.** Die Unversehrtheitsprüfung verglich Original und Ergebnis
  in der gedrehten Anzeige, rechnete ihre Schwärzungszonen aber ungedreht –
  auf einer Seite mit Drehvermerk lag die eigene Schwärzung deshalb neben
  ihrer Zone und galt als Schaden. Solche Seiten behalten jetzt ihre
  Textebene und Vektorgrafik.
- **Auch gerade Seiten wurden gelegentlich ohne Not in ein Bild umgewandelt**,
  wenn der Text hinter einem Platzhalter um einen Punkt nachrückte – erlaubt,
  aber der Bildvergleich war feiner als seine eigene Toleranz. Er vergleicht
  jetzt in halben Punkten und trifft seine Toleranz damit genau: bis zwei
  Punkte Versatz schlägt nichts an, darüber alles.
- **Angaben in eingebetteten Formular-Objekten blieben stehen.** Manche
  Vorlagen legen Briefkopf oder Briefschluss als eigenes Formular ab, das
  die Seite nur einbindet. Ein Treffer darin wurde zwar geplant und als
  entfernt gezählt, aber nie geschrieben – der Text stand weiter da, und
  nur die Rasterung der ganzen Seite fing ihn auf. Jetzt wird das Formular
  selbst umgeschrieben; ein Formular, das auf mehreren Seiten liegt, ein
  einziges Mal.
- **PDF-Seiten wurden zu einem Bild gerastert, obwohl nichts lesbar
  geblieben war.** Ein siebenseitiges Angebot traf es auf sechs Seiten; es
  wuchs von 73 kB auf 3,3 MB und verlor seine Schrift an ein Abbild.
  Ursache waren Leerzeichen, die im Dokument mehrfach hintereinander
  stehen, vom Leser aber nur einmal gemeldet werden: Der Text hinter einer
  entfernten Angabe rückte um ihre Breite nach rechts, die Nachprüfung fand
  das Nachbarwort im Fundrechteck und griff zur Rasterung. Behaltene
  Zeilenreste stehen jetzt wieder exakt an ihrer Stelle; dasselbe Angebot
  wird ohne eine einzige gerasterte Seite bereinigt (76 kB).
- **Schlüsselnamen und Rechnungsköpfe galten als Personen.** In einer
  Zugangsdatei wurde der Name der Umgebungsvariablen („AWS_ACCESS_KEY_ID")
  ersetzt, nicht nur ihr Wert; auf einer englischen Rechnung fiel die
  Überschrift „Bill to" als Vorname. Ein Bezeichner in Versalien mit
  Unterstrichen ist nie ein Name, und ein Wort in einer Zeile, die als
  Ganzes eine Feldbeschriftung ist, auch nicht – der Empfänger darunter
  wird weiterhin gefunden.
- **Die Suche im Nachbessern-Fenster stockte bei großen PDF-Seiten.** Jeder
  Buchstabe im Suchfeld ließ die Seite neu rastern, obwohl sich nur die
  Hervorhebung änderte. Das gerenderte Seitenbild bleibt jetzt stehen,
  solange Seite, Zoom und Ansicht dieselben sind – auch das Original in der
  Vergleichslupe; Blättern, Zoomen und ein neuer Dateistand zeichnen wie
  bisher frisch.
- **Positionsnummern in Angeboten galten als IP-Adresse oder Rufnummer.**
  Eine Artikelzeile wie „1.3.3.4 … 5-Port Gigabit Switch" ließ die
  Gliederungsnummer zur Netzadresse werden, weil „Port" als technisches
  Umfeld zählte – jetzt zählt es nur noch als eigenständige Angabe („Port
  80"), nicht als Wortteil. Und „1.3.3.6 216879" (Positions- plus
  Artikelnummer) wird nicht mehr als Rufnummer geschwärzt. Echte
  IP-Adressen und Rufnummern in solchen Listen bleiben erkannt.
- **Artikelzeilen in Angeboten galten als Postleitzahl mit Ort.**
  „35252 DIETZEL SALR" (Artikelnummer samt Hersteller) und „1000 AWG"
  (Menge samt Leiterquerschnitt) wurden in nummerierten Positionszeilen
  als Anschrift geschwärzt, weil ein Großbuchstabenwort hinter einer
  Zahl als Ortsname in Versalien galt. In Positionslisten gilt das nicht
  mehr; „1080 WIEN" im Anschriftenblock und Orte in Kleinschreibung
  bleiben überall erkannt.
- **Die zusätzliche Namenserkennung schwärzte in Angeboten Rollenzeilen
  und Spaltenköpfe.** „Partiestundensatz Monteur + E-Helfer" galt 49-mal
  als Person, der Spaltenkopf „Pos. Bezeichnung Menge EH" 19-mal als Ort
  – ein 19-seitiger Auftrag wurde dadurch unlesbar. Solche Treffer in
  Positionszeilen fallen jetzt, wenn sie selbst Zeichen tragen, die kein
  Name hat (Plus, Schrägstrich, Ziffer, Kürzel) – auch dann, wenn die
  Zeile mit einem Betrag endet („Alternativ Markt … - PV/LS AC-Versorgung
  1 290,00"). Namen in Verzeichnissen und Listen – wofür die Stufe da
  ist – bleiben unberührt.
- **„Der Kunde" machte in Geschäftsbedingungen jedes „Kunde" zum Namen.**
  Nahm die zusätzliche Namenserkennung den Artikel in den Treffer, galt
  der als zweiteiliger Name und schützte alle 35 weiteren Stellen
  desselben Worts. Jetzt wird der Artikel abgezogen, und „der Kunde"
  fällt wie bisher schon „des Kunden".
- **Beschriftungen galten als Wert.** „E-Mail" wurde siebenmal als
  E-Mail-Adresse, „Telefonnummer" und „Faxnummer" als Rufnummer
  geschwärzt. Eine Adresse ohne @ und eine Rufnummer ohne Ziffern
  zählen nicht mehr.
- **Spaltenkürzel aus einem Buchstaben („L: 154,50", „S: 0,00") galten
  als Name** – 25-mal in einem PV-Angebot. Ein einzelner Buchstabe ist
  weder Name noch Ort.
- **PDF-Seiten wurden viel zu oft in ein Bild umgewandelt.** Zwei
  Ursachen, beide an echten Angeboten gefunden: Setzt ein PDF jede
  Glyphe als eigenen Befehl und steckt darunter ein Leerzeichen-Glyph
  ohne Textzeichen, verschob sich die Zuordnung ab dort um eins – vom
  entfernten Wert blieb der letzte Buchstabe stehen („ŠkodaTopCar**d**"),
  und die Nachprüfung rasterte die Seite zu Recht. Und ein am Zeilenende
  getrenntes Wort („Datenschutz-") galt wegen der Trennstrich-Marke der
  Lesebibliothek als verschoben. Beides behoben: Ein Fahrzeug-Angebot
  ging von 4 gerasterten Seiten auf 0, ein 19-seitiger Auftrag von 7
  auf 0 – die Schrift bleibt Schrift, die Datei bleibt klein.
- **Zwei weitere Rastergründe behoben:** Bringt ein Dokument selbst eine
  Schrift namens „F1" mit, wurden die Platzhalter über Bildern in
  dessen Schrift gesetzt und waren unlesbar – jetzt bekommt die eigene
  Beschriftungsschrift einen freien Namen. Und fehlt der Lesebibliothek
  ein Leerzeichen mitten in einem langen Textbefehl, wird die Stelle
  jetzt auch bei mehrbytigen Schriften bewiesen (gleicher Code, gleiches
  Zeichen) statt ans Ende geraten – vorher blieb dabei ein Buchstabe des
  entfernten Werts stehen und der Resttext rückte sichtbar zur Seite.
  Dazu zwei letzte Fälle: ein Befehl aus Dutzenden Leerzeichen-Glyphen
  ließ die Zuordnung davonlaufen (der Name danach blieb stehen), und
  eine große Überschrift mit Vorbreite fand ihr erstes Zeichen nicht
  (der Firmenname blieb stehen). **Von neun echten Angeboten wird jetzt
  keine einzige Seite mehr gerastert** – vorher waren es 30 von 90.
- **Beim Rastern verschwanden Bilder unter einem schwarzen Block.** Muss
  eine Seite in ein Bild umgewandelt werden, wird sie aus dem Original
  gerendert – und das kennt keine Bildbereinigung. Bisher fiel deshalb
  *jede* Bildfläche der Seite unter einen Balken, auch unberührte. Auf
  einem Angebot steckten Anschrift und zwei Zertifikatslogos in
  demselben Briefkopfbild; der Balken nahm die Logos mit. Jetzt wird das
  bereits bereinigte Bild eingesetzt: Die Anschrift darin ist geschwärzt,
  alles andere bleibt zu sehen. Ein entferntes Bild hinterlässt weißes
  Papier statt eines schwarzen Kastens.

- **Bereinigte Scans wurden um ein Vielfaches größer als das Original.**
  Jedes Bild, in dem etwas geschwärzt wurde, ging als unkomprimiertes
  Rohbild zurück in die Datei – bei einem 24-seitigen Scan wuchs sie damit
  von 11,8 auf 52,9 MB. Bilder behalten jetzt die Art, in der sie vorlagen:
  ein Foto bleibt ein Foto, ein Fax-Scan bleibt schwarzweiß, ein farbloses
  Bild wird nicht als Farbbild abgelegt. Dieselbe Datei ist nun 15,6 MB
  groß, ohne sichtbaren Unterschied.

- **Gescannte PDF-Dateien aus Bürogeräten kamen als Streifenmuster zurück.**
  Solche Scans legen die Schrift als scharfe Schwarzweiß-Ebene über ein
  grobes Farbbild – Canon, Xerox und Kofax bauen ihre Dateien so. Beim
  Schwärzen im Bild wurde diese Ebene falsch zurückgeschrieben; das
  Ergebnis war unlesbar. Bei einem sechsseitigen Angebot traf es neun von
  sechzehn Bildern. Sie wird jetzt richtig behandelt, in ihrer eigenen
  Farbe, und die geschwärzten Stellen sind darin wirklich weg.

- **„Alle Bilder entfernen" nahm einer gescannten Seite ihren Text.** Die
  Schriftebene eines solchen Scans ist technisch ein Bild – sie wurde
  mitentfernt beziehungsweise verwischt, und übrig blieb ein leeres Blatt.
  Sie bleibt jetzt stehen; Logos, Stempel und Unterschriften weichen
  weiterhin.

- **Die Prüfung auf beschädigte PDF-Seiten rastert nicht mehr wegen eines
  winzigen Versatzes.** Ein beim Bereinigen neu verankertes Textstück darf
  um bis zu zwei Punkte verrutschen; der Bildvergleich zählte das trotzdem
  als Schaden und baute die Seite als Abbild neu – dabei gingen
  Vektorgrafiken wie Tabellenlinien verloren, und über Fundstellen lag ein
  Balken statt eines Platzhalters. Der Vergleich lässt jetzt denselben
  kleinen Versatz zu wie die Wortprüfung; echte Schäden fallen weiterhin
  auf.

- **Das Zurückholen vieler Werte nacheinander scheiterte auf Windows nicht
  mehr an „Zugriff verweigert“.** Wer in einer Office-Datei viele
  Panelzeilen kurz hintereinander zurücknahm, konnte an einer kurzlebigen
  Dateisperre des Virenscanners scheitern; der Austausch wartet solche
  Sperren jetzt kurz ab.

- **Der Windows-Weg der Befehlsübergabe beendete den Prüfer statt zu
  prüfen.** Die Lebendprüfung der lauschenden Instanz schickte auf Windows
  versehentlich ein echtes Strg+C an die eigene Konsolengruppe; sie fragt
  jetzt ohne Signal beim System nach.

- **Mehrwortige Feldbeschriftungen wirkten nicht, dafür wirkten ihre
  Bruchstücke.** „Date of birth", „Bank account", „Cuenta bancaria" und
  „Numero de cliente" standen in der Beschriftungsliste, wurden dort aber in
  Einzelwörter zerlegt und trafen deshalb nie; übrig blieben Wortteile wie
  „de" und „of", die seither als Beschriftung galten – „de" ist aber ein
  Namensbestandteil („Anna de Vries"). Beides ist behoben: Die Wendungen
  wirken jetzt als Ganzes, die Bruchstücke sind fort.

- **Deutsche Grußformeln mit „ß" wurden trotz Eintrag als Personenname
  behandelt.** Unter „Herzliche Grüße" oder „Mit freundlichen Grüßen" stand
  im Ergebnis ein Platzhalter, obwohl beide Wendungen seit jeher in der
  Gegenliste stehen. Ursache war eine Schreibweise, die beim Vergleich nie
  ankam; betroffen waren acht Einträge über fünf Listen. Sie wirken jetzt
  alle.

- **„John Staff" blieb unersetzt.** Ein Nachname, der zugleich eine
  englische Spaltenüberschrift ist, wurde vom Beschriftungsfilter
  mitverworfen. Die Überschrift bleibt weiterhin unangetastet, der Name
  darunter wird wieder ersetzt.

- **Werte aus beschrifteten Formularfeldern bleiben in der KI-Stufe
  geschützt.** Der lokale Schiedsrichter der KI-Stufe bekam bisher auch
  Treffer zur Beurteilung vorgelegt, deren Bedeutung bereits die
  Feldbeschriftung belegt („Geburtsdatum:" über dem Wert) – und durfte sie
  verwerfen. Solche strukturell belegten Werte werden ihm nicht mehr
  vorgelegt. Die Zuordnungsdatei nennt zu jeder Ersetzung jetzt zusätzlich
  den Erkennungsweg („beleg“).

- **Eine PDF-Seite, deren erhaltener Text beim Bereinigen Schaden nahm, wird
  jetzt erkannt und als Abbild des Originals neu aufgebaut.** Bei manchen
  Erzeuger-Schriften konnten erhaltene Textstellen nach der Bereinigung als
  schwarze Blöcke erscheinen oder Wörter zusammenrücken, obwohl alle zu
  entfernenden Angaben korrekt entfernt waren. Maskuro vergleicht das
  Ergebnis nun Wort für Wort und Bildpunkt für Bildpunkt mit dem Original;
  eine beschädigte Seite wird durch ihr sauberes Abbild ersetzt — mit
  Schwärzungsbalken über den Fundstellen, geschwärzten Bildbereichen und
  durchsuchbarem Text. Die Seite bleibt lesbar, die Entfernung verlässlich.

### Geändert

- **In den übersetzten Oberflächen heißt jeder Fachbegriff jetzt überall
  gleich.** Für ein und dasselbe deutsche Wort standen je nach Fenster zwei
  oder drei Übersetzungen nebeneinander: Das Prüfprotokoll hieß auf
  Norwegisch teils „Revisjonslogg", teils „Kontrollogg", die Freistufe teils
  „Gratisnivå", teils „Gratisversjon" – und ähnlich in einem Dutzend
  weiterer Sprachen. Wer eine Einstellung suchte, fand sie im nächsten
  Fenster unter anderem Namen. Vereinheitlicht wurde auf das Wort, das die
  Oberfläche ohnehin am häufigsten führt.

  Dabei kamen Stellen ans Licht, an denen ein Wort für zwei
  **verschiedene** Dinge stand: Französisch, Griechisch und Koreanisch
  benutzten für „schwärzen" und „maskieren" denselben Ausdruck – also
  ausgerechnet dort, wo das Programm den Unterschied erklärt („Schwärzen
  entfernt ersatzlos, Maskieren behält die Form"). Beides ist jetzt
  auseinandergehalten. Für Schwedisch steht diese Entscheidung noch aus:
  Dort heißt das Schwärzen „maskera" – dasselbe Wort wie das Maskieren.

- **Die Frage nach der Nutzungsart beim ersten Start ist entfallen.** Kurz
  nach dem Start kam ein Fenster („Privat oder im Betrieb?"), und in den
  Einstellungen stand dazu eine Zeile. Beides gibt es nicht mehr – ersatzlos.
  Eine Angabe, an der nichts hängt, gibt falsch an, wer die falsche Lizenz
  will, und wer ehrlich ist, braucht sie nicht; gekostet hat sie jeden einen
  Klick zu einem Zeitpunkt, an dem niemand an Lizenzarten denkt. Welche
  Lizenz die richtige ist, steht dort, wo sie entschieden wird: auf der
  Preisseite, in der Kasse und in der Hilfe. Häuser, die Maskuro zentral
  ausrollen, geben die Nutzungsart weiterhin über die Vorgabendatei vor.

- **Die Hinweise zur Lizenzart nennen den Fall, um den es geht.** Die
  Privatlizenz gilt ausschließlich der privaten Nutzung; jede berufliche
  oder gewerbliche Arbeit braucht die Firmenlizenz – auch als
  Einzelunternehmer ohne Angestellte. Das stand so in den
  Lizenzbedingungen, aber weder im Programm noch in der Hilfe: Dort war
  immer nur von der Firmendomäne die Rede, und die erfasst genau diesen
  Fall nicht: Der Rechner eines Selbstständigen gehört keiner Domäne an.
  Der Hinweis beim Einlesen einer Privatlizenz sagt es jetzt,
  ebenso das Lizenzkapitel der Anleitung und die häufigen Fragen, die dafür
  einen eigenen Eintrag bekommen haben. Gesperrt wird weiterhin nichts.

- **Die noch nicht ausgelieferten Wege liegen jetzt beisammen.** Die
  Einstellungen haben eine Seite „Entwickler“ bekommen; dort stehen die
  maximale Erkennung (KI) samt ihrer Gegenprobe, der Wortlisten-Katalog und
  die Ordnerüberwachung. Alle drei sind gebaut, aber in der Fläche nicht
  erprobt – sie sind deshalb nur mit einer Entwicklerlizenz sichtbar, und
  zwar überall gleichzeitig: Die Seite, die Menüeinträge und die Wirkung
  im Lauf hängen an derselben Entscheidung. Ohne diese Lizenz bleibt eine
  früher eingeschaltete KI-Stufe wirkungslos; ihre Einstellung wird nicht
  gelöscht und gilt wieder, sobald der Weg ausgeliefert wird.

### Verbessert

- **„Was gesucht wird" zeigt drei weitere Listen aus der Namenserkennung.**
  Die Anreden, nach denen das folgende Wort als Name gelesen wird; die
  Titel und Rollen, die danach noch **nicht** der Name sind („Herr
  Bürgermeister Huber"); und die achtzig mehrsprachigen Beschriftungen, an
  denen Aktenzeichen, Vorgangs- und Fallnummern erkannt werden. Alle drei
  wirkten schon immer, waren in der Übersicht aber nicht zu sehen.

- **„Was gesucht wird" zeigt zwei bisher fehlende Wortlisten.** Die Anreden
  und Titel, die ein davorstehendes Wort zum Namen machen („Herr", „Frau",
  „Dr."), und die Kürzel der Normungsorganisationen, an denen Maskuro einen
  Normverweis wie „ÖNORM B 2110" von einer Person unterscheidet. Beide
  beeinflussen die Erkennung seit jeher, standen in der Übersicht aber nicht.

- **Positionslisten, Inhaltsverzeichnisse, Ausstattungsaufzählungen und
  Normverweise bleiben lesbar.** Die Erkennung sieht jetzt die Bauform der
  Zeile: Ein geratener Name in einer Gliederungszeile („1.3.1
  Energieerdkabel 1kV“), einer Verzeichniszeile mit Führungspunkten, einer
  Aufzählung („- kabelloses Laden mit Magnetring“), über einer
  Mengen-/Preiszeile, in einem Spaltenkopf oder hinter „mittels“ ist ein
  Sachbegriff und wird nicht mehr ersetzt. Echte Namen bleiben geschützt –
  durch Anrede, Feldbeschriftung und den Beleg an anderer Stelle des
  Dokuments; am Messkorpus verlor keine einzige Angabe ihren Schutz. Im
  Geschäftskorpus sinken die Fehlalarme damit von 25 auf 6.

- **Überschriften, Formularbeschriftungen und Grußformeln werden seltener für
  Namen gehalten – auf Deutsch und Englisch.** Die Wortlisten, mit denen
  Maskuro Sachwörter von Personennamen unterscheidet, sind deutlich
  gewachsen: Beschriftungen aus Rechnungen, Formularen und Behördenpost
  („Aktenzeichen", „Verwendungszweck", „Kostenstelle", „Sort code",
  „Subtotal"), Abschnittsüberschriften von Bewerbungen und Berichten
  („WERDEGANG", „QUALIFIKATIONEN", „SUMMARY", „REFERENCES"), deutsche und
  englische Schriftstückarten („Auftragsbestätigung", „Niederschrift",
  „Timesheet", „Agreement") sowie Befehlsformen aus Anleitungen („Sende…",
  „Select…"). Die englische Seite war dabei bisher auffallend dünn besetzt.

- **Beschriftete Felder verraten jetzt auch dann, was in ihnen steht, wenn
  die Beschriftung zusammengesetzt ist.** „Lieferanschrift",
  „Rechnungsadresse", „Sachbearbeiterin", „Kontoinhaber", „Contact person"
  und „Billing address" ordnen den Wert daneben oder darunter nun derselben
  Art zu wie das schlichte „Anschrift" oder „Name" – im ausgefüllten
  Formular mit Kästchen ist das der Unterschied zwischen gefunden und
  übersehen.

- **Im Nachbessern-Fenster blättert das Mausrad am Seitenrand weiter.** Wer
  am Ende einer Seite weiterrollt, landet oben auf der nächsten; wer am
  Anfang zurückrollt, unten auf der vorigen – ein Dokument lässt sich damit
  von vorn bis hinten durchrollen, ohne die Seitenknöpfe anzufassen. Die
  Tastatur (Bild↑/Bild↓) konnte das schon; eine kurze Atempause zwischen
  zwei Seitenwechseln verhindert, dass der Nachlauf eines Trackpads durch
  das halbe Dokument trägt.

- **Die Seitenminiaturen im Nachbessern-Fenster sitzen mittig im Fach.**
  Bisher klebten sie an der linken Kante, und beim Breiterziehen wuchs nur
  der leere Rand rechts.

- **Die Symbolleiste des Nachbessern-Fensters zeigt ihre Gruppen.** Die
  Trennstriche haben jetzt Luft und Farbe, „Suchen“ und „Auf alle Seiten
  übertragen“ stehen als eigene Gruppen neben den Werkzeugen, und
  „Übertragen“ erscheint nur noch bei Dokumentarten, in denen es etwas
  bewirken kann. Jeder Eintrag in Leiste und Menüs trägt nun ein Bild:
  „Textzeilen“ und die Vergleichslupe haben eigene Symbole bekommen
  (die Lupe teilte sich ihres bisher mit „Vorher/Nachher“), dazu Zoom,
  Ganze Seite, Seitenbreite, Drehen, Blättern und die Tastenkürzel.
  „Mit Systemprogramm öffnen“ steht jetzt auch in der Leiste neben
  Drucken – der Weg vom fertigen Ergebnis ins gewohnte Programm ist ein
  Klick, kein Menügang.

- **Bei der Zwischenablage-Bereinigung steht wieder dabei, dass nachzusehen
  ist.** In den Einstellungen steht der Hinweis dauerhaft neben dem Schalter:
  Maskuro kann personenbezogene Daten übersehen oder Angaben falsch behandeln,
  der eingefügte Text ist vor der Weitergabe durchzusehen. Beim Einschalten
  nennt ihn zusätzlich die Meldung, und er wird im Ausgabebereich vermerkt –
  auch dann, wenn kein Symbol im Infobereich läuft. Bei jedem einzelnen
  Kopiervorgang erscheint er bewusst nicht: Ein Hinweis, der fünfzigmal am Tag
  käme, würde nach dem dritten Mal nicht mehr gelesen.

## 0.10.36-beta.1 – 20. August 2026

### Verbessert

- **Technische Geschäftsdokumente werden nicht mehr zerschwärzt.** Vier
  Erkennungsbremsen, gewonnen aus elf realen Angeboten und Aufträgen:
  Gliederungsnummern („1.3.1.1“) gelten nicht mehr als IP-Adressen,
  Normverweise („ÖNORM EN 62446“) und Kennungscodes nicht mehr als
  Postleitzahl oder Rufnummer, und Rollenwörter hinter Artikeln („der
  Kunde“, „des Auftraggebers“) nicht mehr als Namen – in den Geschäfts-
  bedingungen eines realen Angebots sind damit alle 46 Rollenwörter wieder
  lesbar statt geschwärzt. Anschriften mit Länderkennung („A 3390 Melk“,
  „D-94032 Passau“) werden jetzt vollständig entfernt, statt die
  Postleitzahl als Waise stehen zu lassen.

- **Wortlisten sind jetzt vollständig einsehbar.** Unter „Hilfe →
  Wortlisten …“ lassen sich die örtlich verwendeten Erkennungs- und
  Gegenprüfungslisten samt Sprache, Zweck, Quelle und Inhalt durchsuchen.
  Dazu gehören auch Wordfreq-, Medizin-, persönliche und zentral verwaltete
  Listen sowie die Vorräte für erfundene Ersatzwerte. Das Handbuch beschreibt den Katalog in einem eigenen Abschnitt.

- **Fertige Dateizeilen zeigen die verwendete Erkennungssprache.** Hinter
  „fertig“ steht nun etwa „Deutsch“ oder „Englisch“, damit eine unpassende
  automatische Sprachwahl sofort auffällt. Musste eine andere installierte
  Sprache einspringen, zeigt ein Pfeil beide Sprachen.

- **Die neue Vergleichslupe zeigt beim Durchlesen sofort die passende Stelle
  im Original.** Ihr vergrößerter Originalausschnitt folgt dem Mauszeiger über
  dem weiterhin bearbeitbaren Ergebnis; bei Text folgt er dem Absatz. Die Lupe
  lässt sich an der Fensterkante verwenden oder als eigenes, maximierbares
  Fenster herausziehen. Ihr Zoom ist direkt zwischen 50 und 300 Prozent
  einstellbar und wird ebenso gemerkt wie das Einschalten. „Zurücksetzen“
  bringt auch eine maximierte oder ungünstig angedockte Lupe wieder links in
  eine bedienbare Größe. Ersetzte Originalwerte sind in der Lupe gelb
  hervorgehoben, damit die betroffenen Wörter beim Lesen sofort auffallen.
  Einmal aktiviert, öffnet sie sich bei künftigen
  geeigneten Dokumenten wieder – auch nach einem Programmneustart. Der
  bisherige Vorher/Nachher-Umschalter bleibt im Ansichtsmenü erhalten. Das Handbuch beschreibt sie in einem eigenen Abschnitt.

- **Open-Source- und Modellnachweise sind jetzt releasegenau.** Der Paketbau
  erzeugt eine maschinenlesbare Komponentenliste samt Hashes der beigelegten
  Lizenztexte. MPL-Quellen, Modellherkunft, feste Revisionen, Änderungen und
  SHA-256 werden getrennt nachgewiesen; nachgeladene Modelle erhalten ihren
  Herkunftsbeleg direkt im Modellordner. Bewegliche Tesseract- und spaCy-
  Bezugslisten wurden fest angepinnt. Verkaufsartefakte bleiben gesperrt,
  bis alle Quellen und Modellbeilagen veröffentlicht und geprüft sind.

- **Der örtliche wordfreq-Datenbestand ist vollständig lizenzbelegt.** Der
  Paketbau prüft Version 3.1.1, 39 unveränderte kleine Listen einschließlich
  CJK und die chinesische Zeichenkarte gegen Anzahl, Größe und
  Manifest-Prüfsumme. Apache-2.0-Codehinweis, vollständige CC-BY-SA-4.0-
  Lizenz, Attribution, Datenquellen und die weggelassenen großen, Jieba- und
  nicht unterstützten Listen sind im Paket dokumentiert.

- **Häufige Satzwörter werden seltener irrtümlich geschwärzt.** Ein örtliches
  Häufigkeitswörterbuch dient als zusätzliche Gegenprobe, wenn die
  Namenserkennung ein Verb, Pronomen, einen Artikel oder eine Präposition für
  eine Person hält. Das Wörterbuch entscheidet nie allein: Hauptwörter,
  mehrteilige Namen sowie Namen in Feldern, Listen und nach Anreden bleiben
  geschützt. Chinesisch, Japanisch und Koreanisch verwenden ausschließlich
  exakte Token-Grenzen ihrer bereits vorhandenen Sprachmodelle; für nicht
  vorhandene Sprachen wird keine vermeintlich ähnliche Wörterbuchsprache
  eingesetzt. Dafür wird kein Dokumenttext ins Internet übertragen.

- **Technische Produkt- und Ausstattungsbegriffe werden nicht mehr so leicht
  für Namen oder Orte gehalten.** Die örtliche Gegenprobe verbindet nun
  Häufigkeit, Wortart, technische Wortbildung und Sachfelder. Dadurch bleiben
  beispielsweise „Travel-Assistent", „Family-Bonus", „WLTP-Wert",
  „Easy-Start" und zusammengesetzte Nummern-, Halter- oder Bremsbegriffe im
  Dokument. Englische Bestandteile werden auch in deutschem Sachtext örtlich
  nachgeschlagen; echte Eigennamen, Anreden sowie Personen- und Ortsfelder
  behalten Vorrang. Außerdem gilt eine „2-jährige Herstellergarantie" nicht
  mehr als Lebensalter.

- **Die Qt-/PySide-Lizenzrechte sind jetzt vollständig nachvollziehbar.**
  Das Programmpaket enthält zusätzlich den GPL-3.0-Gesamttext, genaue
  Qt-Fassungen, ein Quellcodeangebot und eine deutsch/englische Anleitung zum
  Austausch der dynamischen Bibliotheken einschließlich lokaler
  macOS-Neusignierung. Ein Verkaufsbau wird blockiert, solange die exakten
  Quellarchive der ausgelieferten Fassung nicht auf der eigenen
  Quellcodeseite verfügbar sind.

- **Lizenz und Aktualisierungsstand sagen jetzt für jede Stufe eindeutig,
  was gilt.** Im Lizenzfenster und bei den Aktualisierungseinstellungen steht,
  ob Aktualisierungen enthalten sind, bis zu welchem Tag sie reichen und ob
  die laufende Fassung dauerhaft nutzbar bleibt. Privatlizenzen installieren
  nach dem Stichtag keine später erschienene Fassung mehr; auch ein neu
  heruntergeladener Installer erkennt an seinem fest eingebauten
  Erscheinungsdatum, ob der eingegebene Schlüssel ihn umfasst. Die letzte
  gedeckte Privatfassung bleibt dauerhaft nutzbar. Endet dagegen ein
  Firmenabo, enden Nutzung und Aktualisierungen; Testzeitraum und Freistufe
  öffnen sich nicht als Umweg.

- **Private Dauerlizenzen finden nun auch nach einer Neuinstallation den
  richtigen Programmstand.** Ein signierter Versionskatalog führt alle
  stabilen Fassungen und ihre Pakete. Ist der letzte vom Kauf umfasste
  Installer nicht mehr erhältlich, darf stattdessen automatisch genau die
  nächste höhere verfügbare stabile Fassung verwendet werden – niemals eine
  Beta oder Nightly. Bei einer zu neuen Installation kann der Kunde den
  zulässigen Stand installieren oder zur Kaufseite für einen neuen
  Aktualisierungszeitraum wechseln; ein Rückschritt geschieht nicht stumm.
  Das gilt auch für verwaltete MSI-Installationen.

- **Die automatische Gesichtsschwärzung ist jetzt eindeutig beschrieben.**
  Programmhilfe und Datenschutztext nennen die Funktion
  „Gesichtsbereiche erkennen und unkenntlich machen“ und grenzen sie von
  Identifikation, Wiedererkennung, Gesichtsvergleich, biometrischen Vorlagen
  und Personen- oder Gesichtsdatenbanken ab. Sie weisen außerdem klar darauf
  hin, dass die vollständig lokale Erkennung Bereiche übersehen oder
  irrtümlich markieren kann und das Ergebnis deshalb visuell geprüft werden
  muss. Auch bei einer einzeln bereinigten Bilddatei nennt der Ergebnisbericht
  nun erkannte und verpixelte Gesichtsbereiche; eine fehlende Texterkennung
  wird dabei nicht mehr fälschlich als vollständig unveränderte Datei
  beschrieben.

## 0.10.36-alpha.20260820 – 20. August 2026

### Behoben

- **Anonymisierte Angaben lassen sich jetzt unabhängig von der Reihenfolge
  vollständig zurückholen.** Die frühere Rücknahme suchte den Wert über
  sichtbare Textanker. In dichten Tabellen, direkt benachbarten Platzhaltern
  und unsichtbaren Office-/Mail-Ablagen fehlten diese Anker; manchmal wurde
  ein Begriff deshalb erst rückholbar, nachdem ein anderer Klartext zufällig
  einen neuen Anker geschaffen hatte. Jetzt werden Ergebnis und Original je
  echtem Format-Träger mit der vollständigen Zuordnung verglichen und nur die
  belegten Stellen des gewählten Werts geschrieben.

- **Namen, Mailadressen, Nummern und eigene Prüfbegriffe bleiben auch bei
  überlappender Erkennung eindeutig bedienbar.** Ist derselbe Klarwert zwei
  Arten zugeordnet, entscheidet der tatsächlich an der Fundstelle stehende
  Platzhalter zusammen mit der angeklickten Sidebar-Zeile. Ein nicht belegtes
  Wert/Platzhalter-Paar bleibt weiterhin sicher gesperrt.

- **Mail-Sonderfälle hinterlassen keine versteckten Platzhalter mehr.** Das
  gilt für MIME-kodierte Betreffe, Textanhänge und über HTML-Markup getrennte
  Namen in EML und MSG. UTF-8-HTML ohne eigene Zeichensatzangabe wird in
  Outlook-Dateien außerdem nicht mehr bei jedem Bearbeitungsschritt zu
  Mojibake umkodiert; ältere, bereits so geschriebene Ergebnisse bleiben
  rückholbar.

### Verbessert

- **Eine neue Freigabematrix bedient jede anonyme Sidebar-Zeile einzeln und
  absichtlich rückwärts.** Sie prüft alle 14 Text-, Office-, Web- und
  Mailformate sowie PDF, anschließend auch Formeln, Attribute, Beziehungen,
  Kommentare, Mailköpfe, Anhänge und interne Nebenablagen. Der vollständige
  macOS-Lauf umfasst jetzt 149/149 grüne Prüfskripte.

## 0.10.35-alpha.20260820 – 20. August 2026

### Verbessert

- **Sprachmessungen vergleichen jetzt wirklich Gleiches mit Gleichem.** Der
  regelmäßige Messkorpus enthält dieselben 14 Dokumentfälle mit denselben
  sieben Text- und vier Bildaufgaben auf Deutsch und Englisch. Ein Vollauf
  wiederholt exakt diese Matrix für alle zwölf vorhandenen Korpussprachen.
  Formulare, Tabellen, Chats und andere noch nicht vollständig übersetzte
  Strukturproben bleiben erhalten, werden aber getrennt ausgewiesen und nicht
  mehr in Sprachquoten gemischt.

- **Der Vollauf schreibt für jede Sprache einen eigenen Messbericht.** Ohne
  Sprachschalter werden bewusst Deutsch und Englisch geprüft;
  `--alle-sprachen` fordert den vollständigen Zwölf-Sprachen-Korpus an und
  bricht vor dem ersten Dokument ab, wenn eine Sprache oder ein Fall fehlt.
  Gleichnamige Ergebnisse liegen in getrennten Sprachordnern. Der
  Gesamtbericht nennt neben der gewichteten Fundquote auch den ungewichteten
  Mittelwert der Sprachquoten.

- **Der offene Sprachvergleich zeigt jetzt auch seine tatsächliche Grenze.**
  Im regelmäßigen Lauf mit Texterkennung entfernen Deutsch und Englisch
  218/218 bekannte Angaben ohne Fehlalarm. Der Volltest mit Texterkennung und
  Hoch-Stufe entfernt 1.255/1.308 Angaben bei 17 Fehlalarmen; elf Sprachen
  erreichen 100 Prozent, Hindi 51 Prozent. Frühere Vollquoten beruhten auf
  ungleichen Dokument- und Sollmengen und sind mit der neuen Matrix nicht
  vergleichbar.

## 0.10.34-alpha.20260819 – 19. August 2026

### Behoben

- **Mehrfach vorkommende Namen bleiben nach einer einzelnen Rücknahme in der
  Sidebar erreichbar.** Bisher verschwand die ganze Namenszeile bereits nach
  der ersten zurückgeholten `[NAME]`-Stelle. Weitere Stellen desselben Namens
  blieben dadurch als Platzhalter stehen und wurden zeitweise sogar blockiert,
  bis andere Namen zurückgeholt waren. Jetzt verschwindet die Zeile erst nach
  der letzten Stelle; bereits zurückgeholter Klartext wird trotzdem nicht
  erneut automatisch anonymisiert. Das gilt ebenso für eine teilweise
  gelungene Sammelrücknahme und für das Rahmenwerkzeug in PDFs.

- **„Ersetzung zurücknehmen“ funktioniert auch aus der Office-Seitenansicht.**
  Die sichtbare Seite ist dort nur eine flüchtige PDF-Vorschau; geändert wird
  nun korrekt das Word-, Tabellen- oder Präsentationsdokument darunter und
  anschließend die Vorschau erneuert.

- **Die Rücknahme holt jetzt auch die versteckten Gegenstücke eines Werts
  vollständig zurück.** In Word-, OpenDocument-, Excel- und PowerPoint-Dateien
  können dieselben Angaben zusätzlich in Formeln, Kommentaren, Diagrammen,
  Feldwerten, Alternativtexten und Verweiszielen liegen; HTML, EML und MSG
  führen sie außerdem in Attributen, JSON, Nachrichtenköpfen und Anhängen.
  Bisher blieb dort je nach Format ein Teil als Platzhalter stehen. Jetzt kann
  jede im Trefferbereich angebotene Angabe unabhängig und in beliebiger
  Reihenfolge zurückgenommen werden. Bewusst entfernte Metadaten,
  Änderungsverläufe und Transportköpfe bleiben aus Sicherheitsgründen
  weiterhin entfernt.

- **Beim Zurückholen aus Bildern bleibt keine schwarze Randlinie mehr stehen.**
  Rechte und untere Kante eines Rahmens wurden beim Kopieren aus dem Original
  um je einen Bildpunkt zu knapp ausgelegt. Die Koordinaten stimmen nun mit
  der Schwärzung überein.

### Verbessert

- **Die Freigabeprüfung schickt jetzt jede der 22 unterstützten Dateiendungen
  durch eine vollständige Rundreise.** Inhaltsreiche Dateien werden bereinigt,
  alle angebotenen Werte wiederhergestellt und anschließend tief geprüft.
  Dazu kommen echte Sidebar-Bedienung, pixelgenaue Bildvergleiche und ein
  sichtbarer LibreOffice-Render aller sieben Büroformate. Die kleinen
  Regressionstests bleiben dort bestehen, wo sie einen eigenen Fehler- oder
  Sicherheitsfall abdecken; eine nachweislich doppelte HTML-Prüfung und der
  Test des entfernten Schwarzweiß-Modus sind entfallen.

- **Der vollständige Messkorpus dieser Fassung liegt zum Nachmessen bereit.**
  Das Paket enthält 294 synthetische Dokumente in zwölf Formaten und zwölf
  Sprachen, 2.564 bekannte Angaben, vier maschinenlesbare Solllisten und eine
  Anleitung. Der Download auf der Qualitätsseite verwendet einen
  inhaltsabhängigen Dateinamen, damit Browser nicht versehentlich eine ältere
  Fassung aus dem Cache liefern.

## 0.10.33-alpha.20260819 – 19. August 2026

### Neu

- **Auch in Bilddateien lassen sich einzelne Stellen jetzt aus dem Original
  zurückholen.** Das Rahmenwerkzeug „Original zurückholen“ kopiert die
  Bildpunkte an derselben Position aus der unangetasteten Quelldatei zurück.
  Der Weg bleibt gesperrt, wenn die Quelle fehlt oder andere Bildmaße hat;
  dadurch kann kein Inhalt aus einer verschobenen Stelle eingesetzt werden.

### Verbessert

- **Manuelle Schwärzbalken rasten standardmäßig an Textzeilen ein.** Ein Zug
  über mehrere Zeilen erzeugt je Zeile einen gleichmäßig hohen Balken und
  lässt den Weißraum dazwischen frei. Für Unterschriften, Grafiken und andere
  Sonderfälle schaltet „Freier Rahmen“ zur selbst gewählten Höhe zurück.

- **Der Editor erklärt den nächsten Handgriff direkt über dem Dokument.** Der
  Hinweis wechselt mit Dokumentart und Werkzeug und sagt, ob ein Wortklick,
  eine Textauswahl oder ein Rahmen erwartet wird. Zusätzlich zeigen Werkzeug,
  Mauszeiger und Live-Vorschau schon vor dem Loslassen, was geschehen wird.

### Entfernt

- **Die fehleranfällige Schwarzweiß-Ausgabe wurde entfernt.** Bei manchen PDFs
  blieben unsichtbare Textfelder gegenüber der gerasterten Seite verschoben;
  die scheinbare Dateiverkleinerung war dieses Sicherheits- und
  Darstellungsrisiko nicht wert. Normale PDF-Bereinigung und das gezielte
  Rastern problematischer Seiten bleiben erhalten.

## 0.10.32-alpha.20260819 – 19. August 2026

### Neu

- **Die Ordnerüberwachung läuft jetzt wirklich im Hintergrund.** Eingang,
  Ausgang und Regeln stehen auf einer eigenen Seite unter „Einstellungen“.
  Gestartet und angehalten wird sie über das Maskuro-Symbol in der Task- oder
  Menüleiste; der Eintrag erscheint nur mit der dafür freigeschalteten
  Lizenz. Das Einstellungsfenster kann danach geschlossen und das
  Hauptfenster ins Symbol gelegt werden, ohne die Überwachung zu beenden.

- **Der Nachbessern-Editor hat jetzt einen dauerhaften Lernmodus-Schalter.**
  Er steht im Trefferbereich und im Menü „Werkzeuge“. Wird er ausgeschaltet,
  erscheinen weder beim Zurückholen noch nach manuellen Korrekturen Fragen
  zum Anlegen eigener Regeln. Maskuro merkt sich die Wahl für alle künftig
  geöffneten Dokumente; die Rücknahme selbst funktioniert unverändert.

### Behoben

- **Das große Zusatzmodell lässt sich wieder laden.** Der öffentliche
  Speicher wies Pythons allgemeine Standardkennung mit 403 ab. Modellabrufe
  verwenden nun denselben ausgewiesenen Maskuro-Netzweg wie die übrigen
  eigenen Dienste; die knapp 596 MB große Datei und ihre Prüfsumme bleiben
  unverändert.

- **Eine maximierte Vergleichslupe bleibt beim Andocken nicht mehr als
  schmaler Balken an der Oberkante hängen.** Vor dem Andocken wird ihr freier
  Fensterzustand normalisiert. Ein gespeicherter Maximiert-Zustand wird beim
  nächsten Öffnen ebenfalls in eine veränderbare Größe zurückgeführt.

- **Eine Sammel-Rücknahme holt in Tabellen und anderen Textformaten jetzt
  wirklich alle ausgewählten Werte zurück.** Bei anonymisierten Platzhaltern
  wie `[EMAIL]` schrieb Maskuro die Werte bisher nacheinander. Sobald der erste
  ersetzt war, rückten die Nummern aller verbleibenden Fundstellen vor, der
  bereits berechnete Plan zeigte aber noch auf die alten Nummern. Dadurch kam
  nur ein Teil der Auswahl zurück. Jetzt werden alle gewählten Werte desselben
  Platzhalters gemeinsam und mit stabilen Fundstellennummern geschrieben.
  Wird eine Stelle erst durch einen anderen zurückgeholten Wert eindeutig,
  prüft Maskuro sie im selben Zug erneut – die Reihenfolge der Auswahl spielt
  damit keine Rolle mehr.

- **„Ersetzung zurücknehmen“ lässt in PDFs keine ausgewählten Werte mehr
  aus.** Stand ein Platzhalter sehr knapp hinter einem anderen Wort oder hing
  im Original ein Komma direkt am Wert, konnte die Lageprüfung das Nachbarwort
  beziehungsweise Satzzeichen irrtümlich dem Wert zurechnen. Beim gemeinsamen
  Zurückholen blieben dann einzelne Platzhalter und Trefferzeilen stehen. Die
  Prüfung richtet sich jetzt am tatsächlichen Wortanfang aus und berücksichtigt
  auch eine abweichende Seitendrehung zwischen Original und Ergebnis.

- **Zurückgeholter PDF-Text behält jetzt seine ursprüngliche Größe.** Bisher
  diente der bereits kleiner gesetzte Platzhalter als Maßstab; zusätzlich galt
  auch für den Originaltext die für Platzhalter gedachte Obergrenze von
  11 Punkt. Jetzt werden Originalkasten und Originalschriftgröße aus der
  Quelldatei übernommen – beim Rahmen-Werkzeug ebenso wie beim Zurückholen aus
  dem Trefferpanel.

### Verbessert

- **Der Prüfhinweis benennt das Restrisiko jetzt klarer.** Er sagt
  ausdrücklich, dass Maskuro Daten übersehen oder Angaben falsch behandeln
  kann, und fordert vor jeder Veröffentlichung oder Weitergabe zur
  vollständigen Prüfung und nötigenfalls zur Korrektur von Hand auf. Das
  gilt auch für den Text aus der Zwischenablage und ist in allen 17
  Übersetzungen vollständig nachgezogen.

- **Das Prüfprotokoll startet nun auch innerhalb seiner Zeilen ohne
  Anwendernamen.** Das Protokoll selbst bleibt ausgeschaltet, bis ein Haus es
  bewusst aktiviert. Danach steht ohne zusätzliche Unternehmensvorgabe weder
  in einer Zeile noch im Namen einer zentralen Monatsdatei ein Benutzername;
  dort dient ein nicht erratbares, nur aus dem zufälligen örtlichen
  Profilgeheimnis abgeleitetes Pseudonym zur sicheren
  Trennung. Der Lizenzdialog empfiehlt die Aktivierung nicht mehr, setzt
  „Ohne Protokoll“ voraus und weist vorab auf Betriebsrat,
  Personalvertretung und Datenschutz hin.

- **Ersetzen benennt jetzt, was es ersetzt.** Ein markierter Name wird zu
  `[NAME_3]`, ein Ort zu `[ORT_1]`, eine Rufnummer zu `[TELEFON_2]` –
  statt wie bisher alles zu `[BEGRIFF_n]`. Erkannt wird die Art beim
  Klick; ist sie nicht eindeutig – ein gewöhnliches Wort, oder ein Name
  *und* ein Ort in einer Auswahl –, bleibt es beim allgemeinen Begriff.
  Ein Platzhalter, der eine Art behauptet, die nicht stimmt, wäre
  schlechter als einer, der keine nennt.

- **Die Werkzeuge im Nachbessern-Fenster haben jetzt eine Taste.**
  **S** schwärzt, **E** ersetzt, **Z** holt das Original zurück, **V**
  verpixelt. In der Textansicht wirken sie sofort auf die Markierung, auf
  der Seitenansicht wählen sie das Werkzeug. **Die Buchstaben folgen der
  Sprache**, in der Sie das Programm bedienen – englisch B/R/O/P,
  italienisch O/S/R/P –, denn eine Merkhilfe hilft nur in der eigenen
  Sprache. Die Taste steht am Knopf.
  Wer gerade in der Suchleiste tippt, schreibt weiter Buchstaben – dort
  greifen sie nicht.

- **Das Programm meldet einmal am Tag, in welchem Zustand es läuft – ohne
  jede Kennung.** Damit zählen wir, wie viele Installationen benutzt werden
  und wie sich das auf Testzeitraum, Freistufe und Lizenz verteilt. Hinaus
  gehen Zustand, Betriebssystem, Fassung, Kanal, Land, Sprache, Umfeld und
  Erkennungsstufe – **nichts über Ihre Dokumente und nichts, woran sich Ihr
  Rechner wiedererkennen ließe**. Zwei Meldungen von Ihnen sehen für uns aus
  wie Meldungen von zwei verschiedenen Leuten; ein einzelner Weg lässt sich
  daraus nicht verfolgen. Was genau gesendet wird und wie es sich abschalten
  lässt, steht im Datenschutztext unter Punkt 5.

- **Quer eingezogene Seiten stehen jetzt von selbst richtig herum.** Ein
  Blatt, das schief gescannt wurde, ohne es zu vermerken, erkennt das
  Nachbessern am Textlauf und richtet die Ansicht auf. Wo das nicht geht –
  bei einem reinen Scan ohne lesbaren Text –, drehen zwei neue Einträge im
  Menü „Ansicht“ von Hand (Strg+Umschalt+L und Strg+Umschalt+R). Gedreht
  wird nur die Anzeige: An der Datei ändert sich dabei nichts, und
  Schwärzen trifft weiterhin genau die Stelle, auf die man klickt.

- **Die lokale Ausgabe führt ihre Lizenzen jetzt vollständig und sichtbar
  mit.** Der Bau ermittelt die tatsächlich gebündelten Python-Pakete, legt
  deren Lizenztexte samt Versionsübersicht unter `lizenzen` ab und bricht bei
  einer Lücke ab. Auch Qt, Tesseract und das Gesichtsmodell haben ihre nötigen
  Texte; die Bedingungen für Maskuro selbst liegen als Lizenzvertrag bei.

- **Man sieht jetzt, in welchem Platzhalter die Schreibmarke steht.** Wer in
  einen Platzhalter klickt, sieht ihn ganz aufleuchten – samt Klammern und
  Nummer. Der Knopf „Auswahl zurückholen“ ging schon vorher
  bei einem bloßen Klick an; nur war nicht zu sehen, welche Marke er
  erwischt. Das Leuchten bleibt auch dann stehen, wenn die Maus zum Knopf
  wandert.

- **Der Mauszeiger sagt jetzt, welches Werkzeug gewählt ist.** Vier Werkzeuge
  teilen sich dieselbe Fläche und dieselbe Geste; bis jetzt sah jede gleich
  aus. Fadenkreuz heißt schwärzen, geschlossene Hand ersetzen, offene Hand
  zurückholen.

- **Ein präpariertes Office-Dokument weist jetzt das Programm selbst ab.**
  Eine Word-, Excel- oder OpenDocument-Datei kann Anweisungen mitbringen, die
  beim Öffnen eine fremde Datei Ihres Rechners in ihren Text holen oder den
  Arbeitsspeicher volllaufen lassen. Beides wurde auch bisher abgewiesen –
  aber von der eingebauten XML-Bibliothek, nicht von Maskuro. Jetzt
  entscheidet das Programm es selbst, unabhängig davon, welche Fassung
  dieser Bibliothek im Paket liegt. Für gewöhnliche Dokumente ändert sich
  nichts.

### Behoben

- **Das Trefferpanel entfernt jetzt geschwärzte Platzhalter.** Wurde etwa
  `[NAME_1]` im Nachbessern-Fenster geschwärzt, blieb seine Wertzeile bisher
  rechts stehen, obwohl es im Dokument keine solche Stelle mehr gab. Die
  Zeile fällt jetzt mit der letzten Fundstelle; kommt derselbe Platzhalter
  noch an einer anderen Stelle vor, bleibt sie erhalten.

- **Beim Zurückholen auf einer gedrehten Seite bleibt das Nachbarwort nun
  stehen.** Der Schwärzbalken ragt absichtlich ein wenig über den Text
  hinaus; schon dieser schmale Rand konnte bisher ein angrenzendes Wort wie
  „im“ mitnehmen. Jetzt zählt nur noch eine deutliche Überlappung, nicht die
  Berührung am Rand.

- **Eine zweite Ersetzung in derselben Zeile nahm den Nachsatz mit.** Wer
  „Sachbearbeitung Quaxi Blubbo übernimmt" zweimal hintereinander
  ersetzte, bekam „Sachbearbeitung [ORT_1] [ORT_2]" – das Wort dahinter
  war ersatzlos weg, ohne jede Meldung. Ursache war der Platzhalter
  daneben: Der Rest der Zeile beginnt nach der ersten Ersetzung mit einem
  Leerzeichen, und die Suche nach seiner Textstelle griff die schließende
  Klammer des Nachbarn ab. Danach war alles um ein Zeichen verschoben.
  Betroffen war jede Zeile, in der zweimal ersetzt oder geschwärzt wurde –
  auch beim Zurückholen daneben.

- **Ersetzen schwärzt nicht mehr, wenn der Platzhalter zu lang ist.** War
  neben dem Wort kein Platz für `[BEGRIFF_2]`, wurde der Bereich bisher
  schwarz übermalt – und damit war auch nicht mehr zu sehen, dass dort
  einmal etwas stand, geschweige denn zurückzuholen. Jetzt wird eine
  kürzere Schreibweise geschrieben: `[BEGR_2]`, `[BE_2]`, notfalls `[B_2]`.
  Die laufende Nummer bleibt in jeder Stufe – an ihr findet das
  Zurückholen die Stelle wieder. Nur wo selbst die kürzeste nicht
  hineinpasst, bleibt es beim Balken.

- **Ersetzen ließ den Text stehen, wenn in derselben Zeile schon geschwärzt
  worden war.** Wer im Nachbessern-Fenster einen Namen aus dem Original
  zurückholte, davon den Vornamen ersetzte (dort war kein Platz – es wurde
  ein Balken) und danach den Nachnamen ersetzte, bekam den Platzhalter
  eingelegt, den Namen aber **nicht entfernt**. Aufgefallen ist es nur an
  der Warnung der Nachschau. Ursache war die Zeile selbst: Nach der ersten
  Schwärzung beginnt ihr Rest mit einem Leerzeichen, und daran fand die
  Suche nach der Textstelle keinen Halt. Das betraf jede zweite Schwärzung
  in derselben Zeile.

- **Eine eingeschaltete erweiterte Erkennung ohne ihr Modell fällt jetzt
  auf.** Der Haken konnte gesetzt sein, während das Modell fehlte – die
  Einstellungen gelten für jede Installation, das Modell liegt aber neben
  dem Programm. Die Bereinigung lief dann ohne die Stufe, ohne ein Wort
  dazu. Jetzt sagt der Haken, dass das Modell fehlt, und das Ergebnis
  trägt eine Warnung. Ihre einmal getroffene Wahl bleibt dabei gespeichert:
  Sobald das Modell geladen ist, wirkt sie wieder.

- **Beim Anonymisieren wird jetzt der richtige Begriff zurückgeholt.** Wer
  mehrere Begriffe von Hand ersetzte und danach einen davon zurückholte,
  bekam immer den **ersten** – aus „Schmidt“ wurde „Müller“. Die Zuordnung
  merkte sich je Platzhalter nur eine Ersetzung, und beim Anonymisieren
  tragen alle denselben Platzhalter; der zweite und jeder weitere Begriff
  fiel dabei weg. Jetzt bekommt jeder Wert seine eigene Zeile – auch in der
  Liste der Ersetzungen, die vorher zu kurz war.

- **In Tabellen lässt sich jetzt auch zurückholen.** In einer CSV oder
  Personalliste stehen die Platzhalter direkt nebeneinander, getrennt nur
  durch ein Semikolon. Bis jetzt konnte das Programm dort nicht belegen,
  welcher Wert an welcher Stelle gestanden hatte, und lehnte ab – bei
  `[NAME]` ging es, bei `[GEBURTSDATUM]` und `[TELEFON]` nicht. Jetzt
  zerlegt es die Zeile an allen Platzhaltern. Bleibt eine Stelle wirklich
  mehrdeutig, sagt es weiterhin ab: Ein falsch zurückgeschriebener Wert
  wäre schlimmer als eine ausbleibende Auskunft.

- **Und die Absage ist jetzt zu sehen.** Sie stand in gedecktem Grau am
  unteren Fensterrand, und der Satz war so lang, dass er abgeschnitten
  wurde – es sah aus, als würde gar nichts passieren. Die Sätze sind
  gekürzt, und die Zeile leuchtet ein paar Sekunden in der Warnfarbe.

- **Eine Rücknahme hält jetzt auch nach dem nächsten Eingriff.** Wer beim
  Anonymisieren mehrere Stellen zurückholte und danach etwas anderes
  ersetzte, fand alle zurückgeholten Stellen wieder ersetzt vor und musste
  von vorne anfangen. Ursache war die Zuordnung: Sie behielt den Wert, und
  der selbsttätige Abgleich für einheitliche Platzhalter holte ihn beim
  nächsten Schreiben zurück. Jetzt gilt: Was Sie zurückholen, bleibt
  zurückgeholt – andere Stellen desselben Werts rührt das nicht an.

- **In Text-, Word-, Excel- und E-Mail-Dateien genügt jetzt wirklich ein Klick
  in den Platzhalter.** Die Meldung dazu stand schon in der vorigen Fassung,
  der Knopf „Auswahl zurückholen" blieb aber gesperrt, solange nichts genau
  markiert war – man kam also gar nicht zu dem Weg, der die Auswahl selbst
  gesetzt hätte.

### Behoben

- **Das Prüfprotokoll verrät den Dateinamen nicht mehr.** Es führt Dateien
  bewusst als Streuwert statt im Klartext, weil ein Dateiname Mandant und
  Streitgegenstand verrät. Dieser Streuwert ließ sich aber durch Raten
  bestätigen – ein Pfad ist keine Zufallszahl. Jetzt geht ein Zufallswert
  dieser Installation in die Rechnung ein: Zählen und Unterscheiden im
  Protokoll funktionieren weiter, Nachrechnen von außen nicht mehr.

## 0.10.31-alpha.20260819 – 19. August 2026

### Verbessert

- **Auch in Text- und Tabellendateien leuchtet der Platzhalter beim Zeigen
  rot auf.** Bisher gab es die rote Vorschau nur auf einer PDF-Seite. Jetzt
  zeigen beide Ansichten dasselbe: Was rot ist, trifft der nächste Zug – und
  ein Klick hinein genügt zum Zurückholen.

- **Ein Klick auf ein Wort genügt – das Rechteck setzt der Editor selbst.**
  Im Nachbessern-Fenster musste man bisher über jede Stelle ein Rechteck
  ziehen. Jetzt reicht ein Klick: Der Rahmen legt sich um das Wort und bleibt
  greifbar, lässt sich also weiter aufziehen oder verschieben. Beim Zeigen mit
  der Maus leuchtet das Wort schon rot auf, so dass man vorher sieht, was der
  Klick träfe. Wo kein Wort steht, zieht man wie bisher einen Rahmen.

- **Man muss mit dem Rechteck nicht mehr genau zielen.** Wer ein Rechteck über
  einen Platzhalter oder eine Schwärzung zieht, meint immer die ganze Stelle –
  nie die Hälfte davon. Der Rahmen wächst deshalb selbsttätig auf das Ganze,
  das er berührt: auf den ganzen Platzhalter, den ganzen Balken oder, auf
  einem eingescannten Blatt, auf die ganze geschwärzte Fläche. Kleiner als der
  gezogene Rahmen wird er nie.

- **Geschwärzt wird jetzt wortweise.** Ein Rahmen über der Hälfte eines Wortes
  schwärzte bisher auch nur die Hälfte – und ein halb geschwärzter Name ist
  noch immer ein Name. Berührte Wörter fallen jetzt ganz; der Nachbar bleibt
  unangetastet.

- **In Text und Tabellen genügt ein Klick in den Platzhalter.** „Auswahl
  zurückholen“ verlangte bisher, dass man den Platzhalter samt eckigen
  Klammern genau markiert. Jetzt reicht es, den Zeiger hineinzusetzen; die
  Auswahl springt sichtbar auf den ganzen Platzhalter.

- **Belgien ist als Land dazugekommen.** In den Einstellungen wählbar; erkannt
  werden dann belgische Rufnummern, die Rijksregisternummer (mit Prüfziffer),
  die BTW-/Unternehmensnummer (mit Prüfziffer), Anschriften in beiden
  Amtssprachen und die Postleitzahl mit Ort. Bisher blieben belgische
  Rufnummern stehen, weil das Land überhaupt nicht im Katalog stand.

- **Der Aktualisierungskanal sagt jetzt, wie früh Sie Neues bekommen – nicht,
  wie weit.** Wer auf „Testfassung" stand, bekam eine neue Vorschau oder eine
  neue stabile Fassung gar nicht erst angeboten und musste den Kanal von Hand
  wechseln, um überhaupt davon zu erfahren. Jetzt wird auch alles angeboten,
  was verlässlicher ist: Testfassung nimmt Testfassungen, Vorschauen und
  stabile Fassungen, Vorschau nimmt Vorschauen und stabile. Umgekehrt nie –
  auf Vorschau wird keine Testfassung angeboten, auch wenn sie neuer ist.

- **Im Einstellungsfenster stehen die Zeilen weiter auseinander.** Die vier
  Seiten benutzten eigene Abstände statt des Rasters, das im übrigen Programm
  gilt; besonders auf der Seite „Erkennung" standen die Kontrollkästchen
  dadurch spürbar zu dicht.

### Behoben

- **Ausgefüllte PDF-Formulare erscheinen bei der Handbearbeitung nicht mehr
  leer.** Maskuro macht dafür ausschließlich die flüchtige Arbeitskopie zu
  statischen Seiten: Eingetragene Werte werden sichtbar und lassen sich
  wirklich schwärzen; auslesbare Formularfelder bleiben nicht verborgen in
  der Datei zurück. Das Original bleibt interaktiv und unverändert.
  Das gilt jetzt auch für dynamische XFA-Formulare: Ein XFA-fähiges PDFium
  baut zunächst Werte und Seitenumbrüche auf, anschließend
  entsteht ein neues PDF ausschließlich aus statischen Bildseiten. Schlägt
  der XFA-Aufbau fehl, wird die Datei sicher abgewiesen statt scheinbar leer
  geöffnet.

- **„Abbrechen" wirkt jetzt auch während der genaueren Erkennung.** Bisher
  sperrte sich der Knopf beim Klick, der Lauf rechnete aber bis zum letzten
  Block weiter – bei einer langen Datei sind das Minuten ohne Ausweg, und der
  Knopf sah dabei so aus, als hätte er gewirkt. Jetzt endet der Lauf beim
  nächsten Block.

- **In CSV-Dateien werden Namen jetzt auch dann gefunden, wenn kein
  Leerzeichen vor ihnen steht.** In `P-1000;Brunnthaler, Elisabeth` klebt die
  Personalnummer über das Semikolon am Namen, und für die Erkennung war das
  ein einziges Wort ohne Namen darin – in Personallisten blieb dadurch je
  nach Zeile der ganze Name stehen. Rufnummern, Formeln und die Spaltenzahl
  der Datei bleiben davon unberührt.

- **Ein Name, dessen Vor- und Zuname beide einen Bindestrich tragen, wird
  jetzt erkannt.** „Marie-Luise Habsburg-Ott" blieb mitten im Satz stehen,
  während „Dragan Mitrović" im selben Satz gefunden wurde – ausgerechnet die
  Kombination aus zwei gekoppelten Hälften übersah das Sprachmodell.
  Gekoppelte Sachwörter wie „Nord-Süd-Verbindung" oder „Software-Entwickler"
  bleiben davon unberührt.

## 0.10.30-beta.1 – 18. August 2026

### Verbessert

- **Die Schriftgröße der Textansicht lässt sich jetzt sichtbar einstellen.**
  Der Regler unten rechts, der bisher nur in der Seitenansicht zoomte,
  stellt im Nachbessern-Fenster bei Text- und Office-Dateien die
  Schriftgröße (50–300 %) – ebenso „Vergrößern"/„Verkleinern" im Menü
  Ansicht. Strg+Mausrad konnte das schon immer, aber das wusste nur, wer
  es ausprobiert hatte; jetzt gehen Regler, Anzeige und Rad gemeinsam.

- **Im dunklen Erscheinungsbild liegt jetzt ein weißes Blatt auf dunkler
  Arbeitsfläche.** Bisher war es umgekehrt: Um das Blatt herum blieb eine
  helle Fläche stehen, und der Text selbst stand hell auf dunkel. Jetzt
  bleibt das Blatt in beiden Erscheinungsbildern Papierweiß mit schwarzer
  Schrift – wie eine PDF-Seite, die im Dunkelmodus ja auch nicht dunkel
  wird – und die Fläche darum ist dunkel.

### Behoben

- **Nach einer Schwärzung mitten im Satz geht der Rest des Satzes nicht mehr
  verloren.** Wer im Nachbessern-Fenster dreimal auf dieselbe Stelle ging –
  ersetzen, schwärzen, dann „Original zurückholen" –, bekam den Satzanfang
  gelöscht: Aus „Rückfragen richten Sie bitte an das Rechnungswesen." wurde
  „bitte an das Rechnungswesen.", ohne Warnung. Betroffen war jede Stelle,
  an der schon einmal etwas mitten aus einer Zeile entfernt worden war.

- **Ein Startfehler reißt das Beenden nicht mehr mit.** Wenn der Aufbau des
  Hauptfensters abbricht, stürzte danach auch das Beenden über das
  Taskleistensymbol – und dieser zweite Fehler verdeckte im Fehlerbericht
  die eigentliche Ursache. Jetzt beendet sich das Programm auch aus einem
  halb aufgebauten Fenster sauber, und die gespeicherten Einstellungen
  bleiben dabei unangetastet.

- **„Vorher/Nachher" springt nicht mehr an den Dokumentanfang.** Wer im
  Nachbessern-Fenster nach unten gerollt hatte und zum Vergleich aufs
  Original umschaltete, landete wieder ganz oben – und musste die Stelle
  von Hand wiederfinden. Die Ansicht bleibt jetzt auf derselben Zeile
  stehen, in beide Richtungen.

- **Beim Schwärzen blieb auf Blocksatzzeilen der letzte Buchstabe stehen.**
  Wenn ein Textbefehl mehr Glyphen zeichnet, als die Lesebibliothek
  Zeichen meldet – sie verschluckt in Blocksatz gern ein Leerzeichen –,
  verrutschte die Zuordnung um eins, und aus „Dr. Michael Handler aus
  Willendorf" wurde „[NAME] r aus f": zwei stehengebliebene Buchstaben
  mitten im bereinigten Satz (gefunden an einem echten Ratsprotokoll).
  Die Zuordnung wird jetzt am Wortlaut des Befehls selbst nachgeprüft,
  wo dieser lesbar ist – geraten wird dort nicht mehr.

- **„Lerchenfelder Gürtel 43/12" wurde nur halb entfernt.** Die
  Anschriften-Muster kannten weder Gürtel, Kai, Lände, Zeile, Markt noch
  Graben als Straßengrundwort, und die Hausnummer durfte keine
  Schrägstrichteile tragen (43/12, Haus/Tür) – die Nummer blieb neben dem
  Platzhalter stehen. Beides ergänzt; Wiener und Salzburger Anschriften
  fallen jetzt ganz.

- **Gespeicherte Webseiten bleiben nach der Bereinigung lauffähig.** Die
  Adressen, die Lazy-Loading in data-Attributen ablegt (`data-lazy-src`,
  `data-lazy-srcset`), wurden als Verweise ersetzt – auf einer echten
  Gemeindeseite sechzehn Stück – und die Bilder der Seite luden danach
  nicht mehr. Web-Adressen bleiben dort jetzt stehen, wie in `src` und
  `href` auch; Namen, Mailadressen und Telefonnummern in data-Attributen
  werden weiterhin ersetzt.

- **Japanische und koreanische Dokumente liefen als Chinesisch.** Die
  Spracherkennung warf alle drei Schriften in einen Topf, fand in
  japanischem Text (ohne Leerzeichen) und koreanischem (mit angeklebten
  Partikeln) keine Funktionswörter – und nahm dann schlicht die erste
  CJK-Sprache des Katalogs. Ein japanisches Ratsprotokoll und ein
  koreanisches Sitzungsprotokoll wurden so mit dem chinesischen Modell
  gelesen. Jetzt entscheidet das Schriftbild selbst: Kana heißt Japanisch,
  Hangul heißt Koreanisch.

- **Weitere Fehlgriffe aus dem Feldtest in zehn weiteren Sprachen:**
  Ämter wie „Primar", „Gradonačelnik", „Ordfører", „Başkanı" oder
  „Δήμαρχος" gelten nicht mehr als Personennamen; türkische
  Feldbeschriftungen („Adı", „Soyadı") und griechische Gesprächswörter
  („Ωραία", „Βεβαίως") fallen nicht mehr; Beschluss- und Paragrafenzahlen
  mit Datum („323/25-6-2008", „27 30.09.2024") sind keine Rufnummern mehr;
  und Satztrümmer mit Punkt („10.An", „T.U.EE", „…pa") werden nicht mehr
  als Web-Adressen ersetzt.

### Neu

- **Prüfberichte auf Wunsch automatisch.** Ein Haken in den Einstellungen
  (Seite „Programm") legt nach jeder Bereinigung von selbst ein
  Prüfbericht-PDF ab – mit Zeitstempel im Namen, in einem eigenen Ordner,
  nie neben dem Ergebnis. Nachträglich lässt sich ein Blatt nicht erzeugen;
  wer es für die Akte braucht, hat es damit immer. Voreingestellt ist die
  Ablage aus.

- **Das Prüfprotokoll lässt sich jetzt im Programm einschalten.** Beim
  Einlesen einer Firmenlizenz fragt Maskuro einmal, ob das Protokoll
  geführt werden soll – ein Nachweis trägt nur, wenn er von Anfang an
  läuft. Dazu gibt es einen Schalter in den Einstellungen (Seite
  „Programm", sichtbar mit Firmenlizenz oder im Testzeitraum); die
  Vorgabendatei der Verwaltung gilt weiter und kann den Wert wie bisher
  erzwingen. Eine eigene Protokollzeile „eingeschaltet" hält fest, seit
  wann geführt wird – damit ist auch der Beginn der Aufzeichnung belegt
  und unterschrieben. Voreingestellt bleibt das Protokoll aus.

- **Die Kennzahlen-Klappe zeigt, was die KI-Stufe getan hat.** Eine neue
  Zeile nennt, wie viele unsichere Treffer das Modell beurteilt, behalten
  und verworfen hat und wie viele es zusätzlich gefunden hat – bisher war
  seine Arbeit unsichtbar, wenn man nicht jeden Wert im Nachbessern-Editor
  anklickte. Nur Zahlen, nie Werte oder Begründungen; ohne KI-Arbeit
  erscheint die Zeile nicht.

- **Zurückholen geht jetzt auch in E-Mails und HTML-Seiten.** In `.eml`,
  `.msg` und gespeicherten Webseiten ließ sich ein Platzhalter bisher nicht
  zurücknehmen – die Anwendung sagte es ehrlich, aber gerade die E-Mail ist
  das Format mit den meisten persönlichen Angaben. Jetzt trägt die Rücknahme
  dort genauso: aus dem Trefferpanel, mit markierter Auswahl und auch bei
  anonymisierten Platzhaltern. Der unsichtbare HTML-Zweig einer E-Mail (das,
  was Outlook wirklich anzeigt) wird dabei mitgezogen, damit Ansicht und
  Nachricht dasselbe sagen.

- **Das Trefferpanel nimmt auch anonymisierte Werte zurück – je Wert.**
  „Ersetzung zurücknehmen" war bei anonymisierten Dateien bisher gesperrt,
  weil „[NAME]" für alle Namen zugleich steht. Jetzt schlägt die Rücknahme
  im Original nach, welche Stelle welchem Wert gehört – im PDF an den
  Koordinaten der Fundstelle, in der Textansicht über den Vergleich mit dem
  Original – und holt genau die Stellen des gewählten Wertes zurück. Die
  Zeilen der übrigen Werte bleiben stehen.

- **Auch anonymisierte Platzhalter lassen sich einzeln zurückholen.** Beim
  Anonymisieren heißen alle Angaben einer Art gleich – „[NAME]" steht für
  jede Person, und bisher hieß es deshalb: einzeln zurücknehmen geht nicht.
  Jetzt wird im Original nachgeschlagen, das ohnehin neben dem Ergebnis
  liegt: In der Textansicht den Platzhalter markieren und „Auswahl
  zurückholen" wählen – zurück kommt genau diese Stelle mit genau ihrem
  Wert. Lässt sich der Wert aus dem Original nicht zweifelsfrei ablesen,
  sagt die Anwendung das, statt zu raten. Eine Zuordnungsdatei entsteht
  dabei weiterhin nicht.

- **Das Nachbessern-Fenster öffnet sich nach der Bereinigung von selbst.**
  Kein Werkzeug findet alles – deshalb gehört der prüfende Blick auf das
  Ergebnis zum Normalfall, nicht zum Extraklick. Wer das nicht möchte,
  schaltet es in den Einstellungen unter „Erkennung" ab („Ergebnis danach
  im Nachbessern-Fenster zeigen").

### Verbessert

- **Die Länderwahl steht neu auf „selbsttätig".** Bisher galt ab Werk der
  Sprachraum der Oberfläche – auf einem deutschen Rechner wurden also auch
  niederländische oder französische Dokumente nur mit den DACH-Erkennern
  bereinigt, und eine Anschrift wie „Universiteitslaan 1" blieb stehen
  (gefunden an echten, öffentlichen Ratsprotokollen). Jetzt richtet sich
  die Länderwahl nach der Sprache des Dokuments; wer in den Einstellungen
  eine feste Auswahl getroffen hat, behält sie.

- **Weniger fälschlich Geschwärztes.** Eine Reihe von Fehlgriffen, gemessen
  am Prüfkorpus und an echten Sitzungsprotokollen in sechs Sprachen, fällt
  weg: Firmennamen mit Rechtsform („Musterfirma GmbH") gelten nicht mehr
  als Person oder Ort, sondern als Organisation; Grußformeln und nackte
  Anreden („Saygılarımızla", „Buenas tardes", ein alleinstehendes „Frau")
  sind keine Namen mehr; Ämter („Bürgermeister", „Sindaco", „Alcalde")
  bleiben stehen; Gesetzes- und Beschlusszahlen („39/2015") und Beträge
  mit Tausenderpunkt („330.000") sind keine Rufnummern mehr; Satzanfänge
  wie „Envíame" oder „Estarei" fallen nicht mehr als Name; ein Treffer
  über eine Leerzeile hinweg zählt nicht mehr als Name. Die
  Rechnungsnummer einer Rechnung bleibt als Belegangabe erhalten –
  Kundennummer und Aktenzeichen fallen weiter.

- **Vor dem Laden des KI-Modells steht jetzt, wofür es gut ist.** Der
  Nachlade-Dialog nennt die Aufgaben des Modells – grenzwertige Treffer
  beurteilen, zusätzliche Namen finden, Regeln und Profile vorschlagen –
  und sagt offen, dass es kein Chat-Assistent ist. Die FAQ beantwortet
  dieselbe Frage ausführlich („Was kann die KI-Stufe – und was nicht?"),
  in allen Sprachfassungen.

### Behoben

- **Prüfbericht-PDFs aus der Kommandozeile lassen sich jetzt durchsuchen.**
  Unter Windows startete der kopflose PDF-Weg ohne eine einzige Schrift –
  jedes Zeichen wurde als Ersatzkästchen gezeichnet, und das Blatt trug
  keinen auslesbaren Text: Wer darin suchen oder etwas herauskopieren
  wollte, fand nichts. Jetzt lädt der Bericht in dem Fall die Schriften des
  Systems nach; der Text ist eingebettet und auslesbar. Berichte aus dem
  Fenster heraus waren nie betroffen.

- **„Original zurückholen" über mehrere Zeilen eines Scans ließ schwarze
  Streifen zwischen den Zeilen stehen.** Auf einer in ein Bild umgewandelten
  Seite räumte der Rahmen nur die Zeilenbänder selbst; die Reste der
  früheren Schwärzung blieben in den Lücken dazwischen. Jetzt teilt sich
  der gezogene Rahmen vollständig auf die Zeilen auf.

- **Ein zweiter Rahmen über einem Platzhalter ließ einen roten Rest stehen.**
  Der Platzhalter ist fast immer breiter als das Wort, das er vertritt; wer
  danach über dieselbe Stelle schwärzte, traf nur seinen Anfang – übrig
  blieb ein Bruchstück wie „RIFF_1]" mitten im Satz, und das Zurückholen
  setzte den Originaltext anschließend an dessen Stelle statt an die des
  Wortes. Ein angeschnittener Platzhalter fällt jetzt immer ganz.

- **Auf einer gedrehten Seite löschte das Schwärzen über einem Platzhalter
  einen unbeteiligten Satz.** Der nachträglich gezeichnete Platzhalter wurde
  beim Entfernen mit dem Text davor verwechselt: Er selbst blieb stehen, die
  Warnung „steht immer noch im Dokument" kam – und an anderer Stelle der
  Seite verschwand ersatzlos ein Satz, der mit dem Rahmen nichts zu tun
  hatte. Ein Platzhalter wird jetzt über seinen Wortlaut wiedergefunden;
  die Kette „ersetzen, schwärzen, zurückholen" geht damit auch auf quer
  eingezogenen Seiten auf.

- **Das Handbuch riet in zehn Sprachen noch zu `python3-tk`.** In der
  Fehlerbehebung stand dort, unter Linux fehle womöglich tkinter – ein Rat
  aus der Zeit vor der Qt-Oberfläche, der niemandem mehr weiterhilft. Jetzt
  steht in allen Fassungen derselbe Absatz wie im Deutschen: Es fehlen die
  Systembibliotheken, die Qt für die Darstellung braucht.

- **Das Lizenzkapitel des Handbuchs stand in allen sechzehn Übersetzungen
  auf altem Stand.** In zehn Sprachen las man dort noch, Windows Server
  brauche eine Firmenlizenz mit Serverzugang und Testzeitraum und Freistufe
  gäbe es dort nicht – seit ein Platz einen Menschen zählt und nicht eine
  Maschine, ist beides falsch. Es fehlten außerdem überall die Auskünfte
  dazu, wann ein belegter Platz wieder frei wird, dass sich die Lizenz
  regelmäßig bestätigt und was dabei übertragen wird, und die Freischaltung
  ohne Internet stand nur als Kurzfassung ohne die drei Schritte und ohne
  den Hinweis, dass der Rechner danach ein Jahr ohne Verbindung arbeitet.

- **Sieben Absätze über das Nachbessern fehlten in zehn Sprachen.** Wer die
  Hilfe auf Dänisch, Finnisch, Französisch, Italienisch, Niederländisch,
  Norwegisch, Polnisch, Portugiesisch, Schwedisch oder Spanisch las, fand
  weder die Seitenansicht für Office-Dateien noch „Von Hand schwärzen" noch
  den ganzen Abschnitt darüber, wie das Programm aus einer Korrektur lernt –
  samt der Tabelle mit den drei Weiten. In „Was erkannt wird" fehlte
  denselben zehn Fassungen der Weg über die Beschriftung im Dokument.

- **Mit eingelesener Lizenz startete das Programm nicht mehr.** Statt des
  Fensters kam „Das Programm konnte nicht gestartet werden" – und zwar bei
  jeder Lizenz, gleich welcher. Ursache war die Zeile in der Lizenzanzeige,
  die kurz vor Ablauf der Prüffrist warnt; sie griff auf etwas zu, das dort
  nicht zur Verfügung stand. Ohne Lizenz – im Testzeitraum und in der
  Freistufe – trat der Fehler nicht auf, deshalb ist er erst jetzt
  aufgefallen.

- **Im Formular bleiben die Feldnamen stehen.** „Geburtsdatum" und
  „Anschrift" verschwanden mit ihrem Wert: Der Platzhalter stand klein und
  rot an der Stelle des *Feldnamens*, das Feld darunter blieb leer. Der
  Feldname gehört nicht zu den Daten – er bleibt jetzt, und der Platzhalter
  steht dort, wo der Wert stand.

- **Fremdsprachige Dokumenttitel werden nicht mehr für Namen gehalten.**
  Über einem italienischen Formular stand „FATTURA", über einem spanischen
  „PERMISO PARENTAL" – beide wurden ersetzt. Die Liste der
  Schriftstückwörter kannte nur die deutschen Entsprechungen.

- **Aus einer Rechnung verschwindet keine Position mehr.** „Materialaufschlag
  1  84,00" wurde für eine Anschrift gehalten und durch einen Ortsplatzhalter
  ersetzt – dem Beleg fehlte danach eine Zeile. Eine Zeile, die mit einem
  Betrag endet, ist eine Position und keine Adresse; echte Anschriften
  („Hauptstraße 1  120,00") bleiben unberührt.

### Geändert

- **„Ordner überwachen …" und die Kommandozeile sind vorerst nicht mehr
  da.** Beide Wege sind gebaut und laufen, aber keiner von beiden ist in
  der Fläche erprobt: Die Ordnerüberwachung hat nie einen
  Windows-Durchgang gesehen, und die Kommandozeile gibt einem Skript zwei
  Dutzend Schalter in die Hand, die bei keinem Anwender je liefen. Was
  unbeaufsichtigt Dokumente verändert, soll das nicht ungeprüft tun –
  deshalb sind sie zurückgezogen, bis der Durchgang nachgeholt ist. Der
  Menüeintrag fehlt, und `--wache` steht nicht mehr in `maskuro --help`.

- **Offen bleibt, was nur liest und was ohnehin gebraucht wird.** Der
  Suchlauf (`--suchlauf`) und das Nachprüfen (`--nachpruefen`) arbeiten
  auf der Kommandozeile weiter – sie ändern keine Datei. Ebenso der Start
  über den Explorer, das Kontextmenü, die Zwischenablage und das Fenster;
  daran ändert sich nichts.

- **„Vom Scanner holen" hat jetzt ein eigenes Kapitel im Handbuch.** Es
  stand bisher am Ende von „Ordner überwachen". Auf dem Mac hieß der Rat
  dort, einen Ordner überwachen zu lassen; jetzt heißt er, die
  eingelesenen Seiten ins Fenster zu ziehen.

### Behoben

- **„Original zurückholen" über mehreren Zeilen zerstörte die Gliederung.**
  Ein Rahmen über einen Platzhalter, einen unveränderten Jobtitel und eine
  zweite Ersetzung legte den ganzen Bereich als **eine** Zeile neu ein –
  aus drei Zeilen wurde eine, und was nicht mehr hineinpasste, wurde zu
  einem Balken. Jetzt wird jede Zeile für sich zurückgeholt.

- **Und unveränderter Text bleibt dabei unangetastet.** Wer über eine
  Ersetzung *und* gewöhnlichen Text zieht, bekommt nur die Ersetzung
  zurück; der Rest wird nicht angefasst. Auch der letzte Rest des alten
  Platzhalters verschwindet dabei – vorher blieb dessen schließende
  Klammer mitten im Satz stehen.

- **Beim Ersetzen bleiben keine Reste des alten Textes mehr stehen.** In
  einer fetten Überschrift stand danach „1. R[BEGRIFF_2]ige [BEGRIFF_1] …
  che" – der Platzhalter saß da, aber Silben des Originals daneben.
  Geräumt wird jetzt der Bereich, den Sie umranden, nicht nur die Kästen
  der Wörter darin.

- **Ein anonymer Platzhalter wird nicht mehr zurückgeholt.** Beim
  Anonymisieren trägt jeder Name denselben `[NAME]`. Das Zurückholen nahm
  den erstbesten Eintrag und schrieb ihn an jede Fundstelle – aus „Georg
  Aigner" wurde „Anna Musterfrau", also ein falscher Name im Dokument.
  Jetzt steht dort, dass sich nicht mehr sagen lässt, welche Angabe gemeint
  war; das Dokument bleibt unangetastet.

### Neu

- **„Original zurückholen" wirkt jetzt auch auf einer gerasterten Seite.**
  Wurde eine Seite in ein Bild umgewandelt, kam bisher eine Absage: Der
  zurückgeholte Text käme unter das Seitenbild. Jetzt wird die Stelle im
  Bild geräumt und der Text darauf geschrieben – wie ein Platzhalter auf
  einem Scan. Der Inhalt kommt dabei aus der Originaldatei, und die ist
  nicht gerastert.

- **„Auswahl zurückholen" steht jetzt als eigener Knopf da.** Es ging schon
  vorher, aber nur, wenn man zufällig einen Platzhalter markierte und
  „Auswahl ersetzen" drückte – eine Funktion, die man nur durch Zufall
  findet, gibt es für den Anwender nicht.

### Geändert

- **In reinem Text, CSV und Outlook-Nachrichten gibt es kein „Auswahl
  schwärzen" mehr.** Diese Formate können keinen Balken tragen; der Knopf
  setzte dort einen Platzhalter und sagte es auch – aber ein Knopf, der
  etwas anderes tut, als er heißt, gehört nicht hin.

- **Ein Werkzeug sagt jetzt, wenn es an dieser Stelle nichts auszurichten
  hat.** Ein Platzhalter lässt sich nicht noch einmal ersetzen, über einer
  Schwärzung wird kein Platzhalter gesetzt, und wo schon das Original
  steht, gibt es nichts zurückzuholen. Bisher taten diese Züge etwas, das
  nach Wirkung aussah, aber keine war.

## 0.10.29-alpha.20260817 – 17. August 2026

### Behoben

- **Im Nachbessern-Fenster wirkt jetzt jeder Rahmen, den man zieht.** Wer
  zweimal an derselben Stelle arbeitete – erst ersetzen, dann schwärzen,
  dann das Original zurückholen –, dessen zweiter und dritter Zug
  verpufften wortlos: Der noch greifbare Rahmen des vorigen Zuges fing ihn
  ab. Dasselbe beim Werkzeugwechsel, bei dem sogar still das alte Werkzeug
  weiterwirkte.
- **Ein zu schmal gezogener Rahmen sagt, dass er zu schmal ist.** Bisher
  leuchtete die Vorschau ein Wort rot an, und beim Loslassen geschah
  wortlos nichts.

- **Outlook-Nachrichten lassen sich endlich nachbessern.** Eine `.msg`
  zeigte im Nachbessern-Fenster „Dieses Format lässt sich hier nicht
  anzeigen" – sie war das einzige unterstützte Format ohne jeden Weg, von
  Hand nachzuarbeiten. Jetzt stehen Absender, Empfänger, Betreff und
  Nachrichtentext benannt in der Ansicht und lassen sich wie in jedem
  anderen Textformat markieren und ersetzen.

- **„Auswahl ersetzen" bleibt in einer E-Mail bei der Auswahl.** Wer einen
  Namen im Fließtext markierte, verlor dabei auch Absender und Empfänger
  aus den Kopfzeilen, und die Meldung nannte einen anderen Platzhalter als
  den, der im Text stand. Jetzt wird der markierte Wert überall ersetzt –
  auch im Absender, wenn er dort steht – und sonst nichts angetastet.

- **Ein Rahmen über mehrere Zeilen zerstört den Text nicht mehr.** Bisher
  entstand ein einziger Platzhalter an einer Stelle: Vom angeschnittenen
  Wort blieb ein Rest daran kleben, und aus der zweiten Zeile verschwand
  der Text ersatzlos – kein Platzhalter, kein Balken, nur eine Lücke. Jetzt
  bekommt jede Zeile ihren eigenen Platzhalter mit dem Wert, der dort
  wirklich stand.

- **„Original zurückholen" wirkt jetzt auch nach einer Schwärzung.** Das
  Fenster meldete Erfolg, und der Text kam nie wieder: Der schwarze Balken
  zählte als Hindernis, sodass für den zurückgeholten Text kein Platz mehr
  war. Der Balken weicht dabei jetzt, und der zurückgeholte Text steht
  schwarz da wie gewöhnlicher Text – nicht rot wie ein Platzhalter.

- **„Original zurückholen" an einer unberührten Stelle tut nichts mehr.**
  Wer den Rahmen über Text zog, an dem gar nichts geändert worden war,
  bekam den Text entfernt und kleiner und verschoben wieder eingesetzt –
  gemeldet wurde Erfolg. Jetzt steht dort, dass es nichts zurückzuholen
  gibt.

### Neu

- **Auch in Word, Excel, PowerPoint, OpenDocument und Text lässt sich
  schwärzen.** Bisher gab es dort nur „Auswahl ersetzen"; ein Balken war
  der PDF-Ansicht vorbehalten, ohne dass es dafür einen Grund gab. Wo ein
  Balken nicht darstellbar ist – in reinem Text und in einer
  Outlook-Nachricht –, wird der Wert wie bisher durch einen Platzhalter
  ersetzt, und das steht auch so in der Meldung.

- **Einen Platzhalter markieren holt ihn zurück.** In der Textansicht
  (Word, Excel, PowerPoint, OpenDocument, Text) genügt es jetzt, den
  Platzhalter zu markieren und „Auswahl ersetzen" zu drücken: Der
  ursprüngliche Wert kommt zurück. Bisher verwies das Fenster dafür auf das
  Trefferpanel.

- **Sprecher in einem Besprechungsprotokoll werden auch dann erkannt, wenn
  ihr Name zugleich ein gewöhnliches Wort ist.** „Gruber: Die Abnahme
  erfolgt kommende Woche." wurde ersetzt, „Bauer: Ich stimme zu." blieb
  stehen – der Nachname sieht für die Erkennung aus wie ein Hauptwort.
  Merkzeilen derselben Bauform bleiben unangetastet: Aus „Achtung: Die
  Anlage ist abzuschalten." wird kein Name.

- **„Sie verwenden die neueste Fassung" wurde auch dann gesagt, wenn gar
  nicht nachgesehen werden konnte.** Weist der Aktualisierungsserver die
  Anfrage ab – weil von derselben Internetadresse zu viele Anfragen kamen
  oder weil er gerade selbst gestört ist –, dann stand das Programm still
  auf seiner alten Fassung und behauptete, es sei die neueste. Genau das
  ist am 17. August auf einem Mac passiert: 0.10.25 blieb liegen, während
  0.10.28 seit Stunden bereitlag.

  Jetzt sagt das Fenster, was los ist, nennt die Uhrzeit der nächsten
  Nachschau – und weist ausdrücklich darauf hin, dass **nicht** feststeht,
  ob die eigene Fassung die neueste ist.

  Meist liegt es dabei nicht am eigenen Rechner: Bei vielen Anschlüssen
  teilen sich zahlreiche Kunden dieselbe Internetadresse, und der Server
  zählt sie zusammen. Deshalb sucht Maskuro die Fassungsliste in diesem
  Fall über einen **zweiten Weg** und findet neue Fassungen meistens
  trotzdem. Bleibt es bei der Absage, wird der Server bis zur genannten
  Uhrzeit in Ruhe gelassen – auch wenn man den Knopf noch einmal drückt;
  nachzutreten verlängert die Sperre nur.

- **Mengenangaben werden nicht mehr für Ortsnamen gehalten.** In einem
  Dienstvertrag verschwand „Vier-Tage-Woche" hinter einem Ortsplatzhalter –
  mitten im Vertragsgegenstand. Solche Wortverbindungen aus Zahl und
  Bindestrich („Drei-Punkte-Plan", „24-Stunden-Dienst") bleiben jetzt stehen.
  Anschriften sind davon ausgenommen: Ein „Zwei-Brüder-Weg" wird weiterhin
  ersetzt.

## 0.10.28-alpha.20260817 – 17. August 2026

### Geändert

- **Lizenzplätze werden jetzt wirklich gezählt.** Bisher meldete sich kein
  Arbeitsplatz jemals beim Lizenzdienst an – eine Zehnplatzlizenz lief auf
  beliebig vielen Rechnern, ohne dass davon jemand erfuhr. Neu: Der Rechner,
  der das Programm startet, nimmt einen Platz; ein Platz wird nach **sieben
  Tagen ohne Start** von selbst wieder frei, sodass ein kaputtes Gerät oder
  ein ausgeschiedener Mitarbeiter nichts auf Dauer blockiert.

  Ein kleiner Überzug wird dabei **nur angezeigt und nicht gesperrt**: Bis zu
  zehn Prozent über der gekauften Zahl arbeiten alle weiter – der neue Laptop
  neben dem noch angemeldeten alten soll kein Fall für die Hotline sein. Wer
  darüber hinaus dazukommt, fällt auf die Freistufe zurück und bekommt das
  gesagt; die Rechner, die zuerst da waren, merken davon nichts.

- **Eine gekaufte Lizenz bestätigt sich regelmäßig.** Gelingt das **30 Tage**
  lang nicht, gilt so lange wieder die Freistufe, bis es wieder gelingt.
  Abgeschaltet wird nichts, und ab einer Woche vorher steht der Hinweis im
  Fenster. Sobald der Rechner wieder ins Internet kommt, erledigt sich das von
  selbst. Testzeitraum und Freistufe melden weiterhin überhaupt nichts – wer
  nie kauft, telefoniert nie.

- **„Ohne Internet freischalten" wirkt endlich.** Die Freischaltung wurde
  bisher zwar geprüft und abgelegt, danach aber von niemandem mehr gelesen –
  sie änderte an den Rechten nichts. Jetzt ist sie der Ausweg für Rechner ohne
  Netzzugang: Sie trägt **ein Jahr**, danach holt man sich mit einem frischen
  Anforderungscode eine neue. Ein Gerät mit Internet braucht man dafür einmal
  im Jahr – der Rechner selbst bleibt dauerhaft offline.

- **Die Freischaltung geht jetzt auch aus dem Kundenkonto** – unter „Meine
  Lizenzen" auf der Website. Dort steht außerdem, welche Rechner an Ihrer
  Lizenz hängen und wann deren Plätze wieder frei werden; das war bisher
  nirgends zu sehen. Die Seite ohne Anmeldung bleibt für alle, die keinen
  Shop-Zugang haben – sie verlangt dafür zusätzlich die E-Mail-Adresse aus der
  Bestellung, damit der Lizenzschlüssel allein nicht genügt.

- **Und im Fenster steht jetzt, wohin mit dem Anforderungscode.** Der
  Papierweg sagte „an einem Gerät mit Internetverbindung eingeben" und nannte
  keine Adresse; die Freischaltseite gibt es längst, aber sie war von nirgends
  verlinkt. Jetzt steht **maskuro.com/lizenz-freischalten** im Dialog, im
  Handbuch und in der FAQ – und auf der Website unter dem Lizenzschlüssel.

- **Der Knopf „Ohne Internet freischalten …" bleibt sichtbar**, auch wenn die
  Lizenz gerade nicht gilt. Vorher verschwand er zusammen mit ihr – also genau
  dann, wenn man ihn braucht.

- **„Alle Plätze belegt" sagt jetzt die Wahrheit.** Der Hinweis endete mit
  „Das Programm arbeitet unverändert weiter"; das stimmt nicht mehr, wenn kein
  Platz zugeteilt wurde. Dort steht nun, dass bis auf Weiteres die Freistufe
  gilt.

### Neu

- **Beim Einschalten der Zwischenablage-Bereinigung steht jetzt dabei, dass
  nachzusehen ist.** Die Meldung nennt seither denselben Satz, der auch am
  Ergebnis einer Datei steht: Maskuro erkennt nicht in jedem Fall alle
  personenbezogenen Daten.

  Hier wiegt er schwerer als anderswo. Bei einer Datei sieht man das Ergebnis,
  bevor man es weitergibt. Bei der Zwischenablage nicht – man kopiert, fügt
  ein, und der bereinigte Text steht schon im Mailfenster. Die Meldung sagt
  deshalb ausdrücklich, den **eingefügten** Text durchzusehen.

  Sie kommt beim Einschalten, nicht bei jedem Kopiervorgang: Was fünfzigmal
  am Tag erschiene, liest nach dem dritten Mal niemand mehr.

- **„Alle kopieren" unter der Liste – und „Alle entfernen" rückt weg.** Der
  neue Knopf legt sämtliche fertigen Ergebnisse auf einmal in die
  Zwischenablage, zum Anhängen an eine Mail oder Einfügen in ein anderes
  Programm. Bisher ging das nur über das Menü und auch dort nur für die
  **ausgewählten** Zeilen – wer alle meinte, musste erst Strg+A drücken.

  Dabei ist die Knopfzeile neu geordnet: Links steht, was etwas hinzufügt,
  rechts hinter einem Zwischenraum, was etwas wegnimmt. „Alle entfernen"
  stand bisher unmittelbar neben „Hinzufügen …", und ein Fehlgriff kostete
  die ganze Liste. Dieselbe Regel gilt seit dem 13. August schon an jeder
  fertigen Zeile.

- **Arbeitsplätze ohne Internet bekommen ihre Sprachmodelle jetzt aus dem
  Haus.** Bereinigen ging dort immer schon ohne Verbindung – das Nachladen
  eines Sprachmodells nicht, und ein Modell wiegt mehrere hundert Megabyte.

  Die Verwaltung stellt die Dateien einmal an einem Rechner mit Verbindung
  zusammen und legt sie auf eine Freigabe, ins Rollout oder auf einen Stick.
  Der Ort wird zentral eingetragen (Feld `modellquelle` in `vorgaben.json`
  oder die Umgebungsvariable `MASKURO_MODELLQUELLE`). Von da an bedient sich
  jedes Nachladen zuerst dort – Sprachmodelle, das japanische Wörterbuch und
  die Hoch-Stufe – und geht nur ins Netz, wenn eine Datei fehlt.

  Die Prüfsummen gelten dabei unverändert. Eine Dateifreigabe im Haus ist oft
  leichter zu beschreiben als ein Release im Netz; sie soll nicht der
  bequemere Weg zu einem untergeschobenen Modell werden.

  Wie ein solcher Bestand entsteht und wie Lizenz und Freischaltung ohne
  Internet laufen, steht in `OFFLINE.md`.

- **„Original zurückholen" – ein Rahmen holt zurück, was zu viel entfernt
  wurde.** Im Nachbessern-Fenster gibt es ein neues Werkzeug: Rahmen über die
  Stelle ziehen, und der Text steht wieder da, wie er im Original stand.

  Das schließt die Lücke, die das Trefferpanel offenließ. Dort ließ sich eine
  Ersetzung nur zurücknehmen, wenn ihr Platzhalter eindeutig war – also nicht
  beim Anonymisieren, wo „[NAME]" bei jeder Angabe dieser Art steht, und
  überhaupt nicht bei geschwärzten Stellen, wo kein Platzhalter übrig bleibt.
  Gerade dort sammeln sich die Fehlgriffe: „Benutzer", „Inventarnummer",
  „Unterschrift" werden gern für Namen gehalten.

  Der Rahmen braucht den Platzhalter nicht: Die **Stelle** kommt aus dem
  Rechteck, der **Inhalt** aus der Originaldatei – derselben, die der
  Vorher/Nachher-Umschalter zeigt. Anonymisiert oder pseudonymisiert spielt
  damit keine Rolle mehr.

  Der zurückgeholte Text steht schwarz da, nicht rot: Er ist wieder Klartext
  und kein Platzhalter. Aus der Trefferliste verschwindet ein Eintrag erst
  dann, wenn sein Platzhalter **nirgends** mehr im Dokument steht – wurde
  derselbe Wert an mehreren Stellen ersetzt, bleibt er für die übrigen
  stehen.

  Auf einer Seite, die in ein Bild umgewandelt wurde, sagt das Werkzeug ab
  und erklärt warum: Der zurückgeholte Text käme unter das Seitenbild zu
  liegen und wäre nicht zu sehen.

### Behoben

- **Beim Zuklappen von „Details" und „Kennzahlen" blieben Bildreste auf dem
  Bildschirm stehen.** Zugeklappt schob sich ein Teil des Inhalts unter den
  unteren Fensterrand und blieb dort über dem Hintergrund liegen, bis
  irgendetwas anderes darüber gezeichnet wurde.

  Beide Bereiche haben eine Mindesthöhe, damit sie offen brauchbar groß sind.
  Die Bewegung beim Zuklappen setzte aber nur die Höchsthöhe herunter – und
  unter seine Mindesthöhe schrumpft ein Bereich nicht. Der Inhalt blieb also
  200 Punkte hoch, während das Fenster sich schon auf 24 zusammenzog; die
  Differenz stand unter dem Rand. Jetzt weicht die Mindesthöhe für die Dauer
  der Bewegung und kommt danach zurück.

- **Das Fenster wurde beim wiederholten Auf- und Zuklappen immer kleiner.**
  Beim Aufklappen wächst es höchstens bis 92 % der Bildschirmhöhe; ist der
  Platz knapp, wächst es also weniger als gebraucht. Beim Zuklappen zog es
  trotzdem den vollen Betrag wieder ab. Jetzt gibt es genau das zurück, was
  das Aufklappen gekostet hat.

- **Ein Rest einer geschwärzten Angabe konnte sichtbar stehen bleiben.** In
  einem Lebenslauf blieben von „*30.12.1991" die Zeichen „*30.1" lesbar im
  Ergebnis – also Tag und Monatsanfang des Geburtsdatums. Das Programm hatte
  den Rest sogar bemerkt und die Seite deshalb in ein Bild umgewandelt; genau
  das machte es schlimmer, denn damit war der Rest zwar nicht mehr
  durchsuchbar, aber weiterhin zu lesen – und nicht mehr zu beheben.

  Die Ursache lag zwischen zwei Prüfungen. Die schärfere von beiden sieht
  nach, ob in der Fläche einer entfernten Angabe noch etwas steht, das dort
  nicht hingehört; sie meldet ihren Befund als Zeichenmenge, weil sich die
  Lesereihenfolge beim Ersetzen verschiebt. Der Rückfall, der solche Stellen
  vor dem Umwandeln übermalt, suchte diese Zeichenmenge als Text auf der
  Seite – und fand sie nie. Übermalt wurde deshalb nichts. Die Stelle war die
  ganze Zeit bekannt und wird jetzt durchgereicht, statt neu gesucht zu
  werden.

  Betroffen war jede Seite, deren Rest allein von dieser Prüfung gefunden
  wurde – unabhängig von Dateiart und Sprache.

- **Auf einem quer eingezogenen Scan fand die Texterkennung nichts.** Wer ein
  Blatt seitlich in den Einzug legt, bekommt eine Datei, in der die Schrift um
  90 Grad gedreht steht. Bisher las Maskuro darin **keine einzige** Angabe –
  und die Datei sah danach unauffällig aus: gefunden wurde nichts, also wurde
  nichts gemeldet, und die Anschrift stand weiterhin lesbar im Bild. Jetzt
  richtet die Texterkennung die Seite selbst auf; am Prüfbild fallen wieder
  alle Angaben.

  Zwei Grenzen offen benannt: Ein **auf dem Kopf** stehendes Blatt (180 Grad)
  liest sie weiterhin nicht, und bei einem sehr schlechten Scan hilft das
  Aufrichten nicht – dort ist zu wenig lesbar, um die Lage überhaupt zu
  bestimmen. Jedes Bild braucht dafür etwa ein Fünftel länger.

### Geändert

- **„Automatisch installieren" heißt jetzt, was es tut.** Der Haken in den
  Einstellungen versprach mehr, als er einlöste: Er lädt die neue Fassung von
  selbst und startet die Installation – die läuft aber **sichtbar** ab und
  will bestätigt werden, unter Windows samt Rückfrage der
  Benutzerkontensteuerung. Wer „automatisch" las, rechnete mit einem Rechner,
  der sich über Nacht selbst aktualisiert, und stand am Morgen vor dem
  Installationsassistenten. Der Haken heißt jetzt „Aktualisierungen
  selbsttätig laden und die Installation starten", mit einem Satz darunter,
  was das bedeutet. Am Verhalten ändert sich nichts – dass Maskuro sich nicht
  unbemerkt austauscht, ist Absicht und bleibt so.

## 0.10.27-alpha.20260817 – 17. August 2026

### Neu

- **Neu: `--ersetzen` für die Anbindung an eine Kanzleisoftware.** Das
  Ergebnis tritt an die Stelle der Quelldatei, statt daneben zu entstehen.
  Damit funktioniert das Aus- und Einchecken einer Kanzleisoftware
  („Öffnen und Bearbeiten“ in der E-Akte) ohne jede Schnittstelle: Die
  Software gibt die Datei heraus und bekommt sie an derselben Stelle
  bereinigt zurück.

  **Dieser Schalter hebelt den ersten Grundsatz aus**, und deshalb gibt es
  ihn nur auf der Kommandozeile – nicht im Fenster – und nur, wenn Ihre
  Verwaltung ihn freigibt (Eintrag `ersetzen` in der Vorgabendatei). Ohne
  Freigabe bricht der Aufruf ab und sagt, warum; stillschweigend eine zweite
  Datei anzulegen wäre der schlimmere Fehler, denn dann würde die
  unveränderte wieder eingecheckt.

  Geschrieben wird erst eine Nachbardatei; erst wenn sie fertig ist, tritt
  sie an die Stelle der Quelle. Ein Abbruch oder Fehler lässt die Quelle
  damit **Byte für Byte unverändert** und hinterlässt kein Bruchstück. Im
  Prüfprotokoll steht die Ersetzung als eigenes Feld – ein Prüfer muss
  wissen, dass die unbereinigte Fassung hier nicht mehr liegt.

- **Das Handbuch erklärt jetzt die Windows-Warnung beim ersten Start.** Neuer
  erster Abschnitt „Windows warnt beim ersten Start – was zu tun ist“, mit
  zwei Bildern und drei Schritten: „Weitere Informationen“ ist ein kleiner
  Link, kein Knopf – genau daran bleiben die meisten hängen –, dann
  „Trotzdem ausführen“.

  Dass dort „Unbekannter Herausgeber“ steht, ist die ganze Aussage der
  Warnung: Die Pakete werden zurzeit ohne Zertifikat ausgeliefert. Wir halten
  es für richtiger, das zu erklären, als es zu verschweigen.

- **Der Rückweg merkt jetzt, wenn Text und Zuordnung nicht zusammengehören.**
  Wer die Antwort zu einem anderen Vorgang einfügt, bekam bisher fremde Namen
  im richtigen Text – kein Fehler, keine Meldung, nur falsch. Maskuro merkt
  sich jetzt, welche Platzhalter der letzte Lauf überhaupt erzeugt hat, und
  meldet jeden, der nicht dazugehört. Stammt keiner davon aus dem letzten
  Lauf, wird nichts eingesetzt und das Fenster sagt warum – statt wie bisher
  eine abgelaufene Frist zu vermuten.

  **Eine Grenze bleibt, und sie steht auch im Handbuch:** Platzhalter werden
  je Lauf durchnummeriert, der erste Name heißt also in jedem Dokument
  `[NAME_1]`. Trägt der fremde Text nur solche Platzhalter, ist die
  Verwechslung nicht zu erkennen.

- **PDF lässt sich jetzt schwarzweiß ausgeben.** Ein Haken bei der
  Betriebsart wandelt jede Seite in ein Schwarzweißbild um – mit unsichtbarer
  Textebene darunter, also weiterhin lesbar und durchsuchbar. Für den Versand
  über beA und ähnliche Wege mit harten Größengrenzen: über unseren
  Messkorpus im Mittel **68 % kleiner** (Kommandozeile: `--monochrom`).

  **Wie viel es bringt, hängt am Dokument** – und das steht auch am Haken:
  Gescanntes und Bildhaltiges schrumpft stark, ein schlankes Textdokument
  ohne eingebettete Schriften kann sogar größer werden. Probieren Sie es an
  einer Datei, bevor Sie es für einen Stapel einschalten.

  Der Preis: Jede Seite wird neu gerechnet – bei tausend Seiten dauert das
  Minuten. Und Abbildungen verlieren alles zwischen Schwarz und Weiß; für
  Text ist das gleichgültig, für ein Lichtbild nicht.

- **Die Trefferliste im Nachbessern-Fenster zählt jetzt mit.** Über der
  Liste steht „5 Treffer“, und sobald Sie filtern, „1 von 5 Treffern“. Das
  ist der Unterschied zwischen „ich habe gefiltert“ und „es sind fünf, und
  ich habe alle gesehen“ – der Handgriff, mit dem man prüft, ob ein Name
  wirklich überall ersetzt wurde.

- **Das Prüfprotokoll lässt sich jetzt durchsuchen und filtern.** Die
  Ansicht unter „Datei → Prüfprotokoll“ hatte bisher eine Tabelle und sonst
  nichts – bei einem Monat mit dreitausend Läufen sah man, dass viel
  geschehen war, aber nicht was.

  Neu sind ein **Suchfeld**, **drei Filter** (Verfahren, Ergebnis, Art) und
  das **Blättern**, dazu drei Spalten, die es vorher nicht gab: **Verfahren**
  (geschwärzt oder ersetzt), **Konfidenz** und **Dauer**. Über der Liste
  steht, wie viel gerade zu sehen ist und wie viel der Filter ausblendet.

  „Als CSV speichern …“ gibt jetzt **das aus, was dasteht** – wer gefiltert
  hat, bekommt das Gefilterte, und die Meldung nennt die Zahl.

  Ein Strich bei Konfidenz oder Dauer heißt, dass für diese Zeile nichts
  gemessen wurde – etwa weil sie älter ist als diese Funktion. Diese Werte
  werden **nicht** nachträglich errechnet. Einen Filter über Anwender gibt es
  weiterhin nicht; eine einzelne Zeile findet die Suche trotzdem.

### Entfernt

- **Der Transparenzhinweis im Fenster „Über dieses Programm" ist wieder
  fort.** Er stand seit 0.10.22-beta.1 dort und sagte, dass die Anwendung mit
  Unterstützung Künstlicher Intelligenz entwickelt wurde. Gefordert ist er
  nirgends, und ausgerechnet in einer Anwendung für Datenschutz las ihn
  mancher als Aussage über die Arbeitsweise – also so, als gingen die
  Dokumente zu einem Dienst im Netz. Bereinigt wird weiterhin ausschließlich
  auf dem eigenen Rechner; das steht dort, wo es hingehört, im Reiter
  „Datenschutz".

### Behoben

- **Das Programm tauschte sein eigenes Symbol gegen ein schlechteres aus.**
  Wer das Kontextmenü aus dem Programm heraus eintrug, hatte danach ein
  anderes Schild in der Taskleiste als nach der Installation – ähnlich, aber
  mit linksbündigen statt mittigen Balken und sichtbar gröber. Dahinter
  steckte ein Notbehelf: Findet das Programm die Symbolvorlage nicht, zeichnet
  es sich selbst eines. Gedacht war das für den Fall, dass **keine** Symbole da
  sind; tatsächlich zeichnete es auch dann, wenn die mitgelieferten längst
  lagen – und überschrieb sie. In einer aus dem Setup installierten Fassung
  gibt es keine Vorlage, also traf es dort jeden. Vorhandene Symbole bleiben
  jetzt unangetastet.

  **Bereits betroffene Installationen holen sich das richtige Symbol nicht von
  allein zurück** – dafür einmal neu installieren.

- **„Objektkennung: OB-4711-22" galt als Anmeldename.** Der Erkenner für
  Benutzernamen prüfte seine Beschriftungen ohne Wortgrenze davor – also griff
  **jedes** Wort, das auf eine davon endet: Objektkennung, Fahrzeugkennung,
  Gerätekennung. Der Wert dahinter wurde entfernt, obwohl er mit einem
  Anmeldenamen nichts zu tun hat.

  Zusammensetzungen, die wirklich gemeint sind – „Benutzerkennung“,
  „Anmeldekennung“ –, stehen einzeln in der Liste und werden weiterhin
  gefunden.


- **Auf Englisch, Griechisch, Japanisch und Koreanisch standen sechzehn
  Platzhalter auf Deutsch im Ergebnis.** Wer die Oberfläche auf eine dieser
  vier Sprachen gestellt hatte, bekam für die neueren Datenarten die
  deutschen Beschriftungen ins Dokument geschrieben – aus einem Passwort
  wurde `[ZUGANGSDATEN_1]` statt `[CREDENTIALS_1]`, aus einem
  Diagnoseschlüssel `[DIAGNOSESCHLUESSEL_1]` statt `[DIAGNOSIS_CODE_1]`.
  Betroffen waren Gesundheit, Diagnose, Medikation, Diagnose- und
  Arzneischlüssel, Religion, Gewerkschaft, politische Meinung, Strafrecht,
  Zugangsdaten, Benutzername, Kartendaten, Koordinaten, Beruf, Betrag und
  Merkmal.

  Die übrigen 44 Sprachen hatten den Fehler nie: Sie holen ihre
  Beschriftungen aus den Sprachdateien, in denen diese Arten von Anfang an
  standen. Genau diese vier Sprachen führen aus einem anderen Grund eigene
  Tabellen – ihre Schrift überlebt den PDF-Zeichensatz nicht, weshalb dort
  lateinische Beschriftungen stehen –, und in diesen Tabellen fehlten die
  neuen Arten schlicht.

  Aufgefallen ist es beim Übersetzen der Katalogseite: Die Website
  versprach englischen Lesern Beschriftungen, die das Programm nicht
  schrieb. Ein Prüfstein hält die vier Tabellen jetzt gegen die Liste aller
  Beschriftungen, die überhaupt entstehen können.

- **Das Regel-Fenster öffnet sich nicht mehr zu klein für seinen Inhalt.**
  Im Reiter „Eigene Suchmuster“ lag die Erklärzeile des Assistenten
  („Gesucht wird: …“) halb hinter dem Feld „Probetext“ – ausgerechnet der
  Satz, an dem man ohne Kenntnis regulärer Ausdrücke prüft, ob die eigene
  Regel das Richtige sucht. Das Fenster hatte ein festes Mindestmaß aus
  einer Zeit mit weniger Reitern und ließ sich daher unter das ziehen, was
  hineinpasst. Jetzt richtet es sich nach seinem Inhalt und geht nur so
  klein auf, wie alles lesbar bleibt.

- **Namen in Tabellenformeln bleiben nicht mehr stehen.** Eine Zelle hat
  mehr als einen Ort für Text, und bisher wurde nur einer geräumt. Stand ein
  Name in einer Formel – `="Frau "&"Sieglinde Ortner"` – oder war er das
  zuletzt gerechnete Ergebnis einer Formel, blieb er unverändert in der
  Mappe, obwohl dieselbe Person in der Zelle daneben ersetzt war. Wer die
  Zelle anklickte, las ihn in der Bearbeitungsleiste.

  Beides wird jetzt ersetzt. Angefasst wird nur, was zwischen
  Anführungszeichen steht: Zellbezüge, Funktionsnamen und Blattnamen bleiben
  unberührt, `=SUMME(K2:K6)` rechnet weiter. Weil derselbe Name überall
  denselben Platzhalter bekommt, findet auch `=SUMMEWENN(A:A;"Huber";B:B)`
  weiterhin seine Zeilen.

- **Diagramme zeigen keine Namen mehr an.** Ein Diagramm speichert eine
  eigene Kopie seiner Achsenbeschriftungen – es zeichnet auch dann noch,
  wenn die Quellzellen längst leer sind. Unter den Balken standen deshalb
  weiter fünf Personennamen, während die Tabelle darüber sauber war. Gilt
  für Tabellen **und** Präsentationen.

- **Benannte Bereiche mit festem Text werden geräumt.** Ein benannter
  Bereich kann statt eines Zellbezugs einen festen Text enthalten; stand
  dort ein Name, blieb er. Der **Name** des Bereichs bleibt weiterhin
  stehen – auf ihn verweisen Formeln, und eine Umbenennung ergäbe einen
  Bezugsfehler. Wie beim Blattnamen wird er gemeldet, nicht ersetzt.

- **Ein einmal erkanntes Geburtsdatum verschwindet im ganzen Dokument.**
  Ein Datum für sich sagt nichts – erst ein Feldwort macht es zum
  Geburtsdatum, und genau darum bleibt ein Rechnungsdatum in Ruhe. Stand
  dieselbe Angabe im selben Dokument aber ein zweites Mal ohne dieses Wort –
  im Bildtitel, in einem ausgefüllten Formularfeld –, blieb sie dort stehen,
  obwohl ein paar Zeilen darüber „geboren am …“ zweifelsfrei erkannt war.
  Übertragen wird nur, was in **diesem** Dokument schon als Geburtsdatum
  erkannt wurde; geraten wird weiterhin nichts.

- **Strukturierte Daten in Webseiten geben ihr Geburtsdatum preis.** Im
  JSON-LD-Block für Suchmaschinen steht das Datum unter dem Schlüssel
  `birthDate` – der Schlüssel sagt, was es ist, so wie sonst die
  Spaltenüberschrift. Er wird jetzt mitgelesen; „Birthday“ und „Birthdate“
  gelten damit auch in Formularen als Feldbezeichnung.

- **Geburtsdatum und Personalnummer werden auch in Tabellen gefunden.** In
  einer Zelle steht nur der nackte Wert – `14.03.1988`. Was er bedeutet,
  sagt allein die Spaltenüberschrift, und die steht viele Zeilen weiter
  oben. In Excel wurde sie bereits mitgelesen; in LibreOffice-Tabellen und
  in CSV-Dateien nicht, und dort blieb das Geburtsdatum deshalb stehen.

  Beide lesen die Überschrift jetzt mit – **aber nur, wenn sie selbst eine
  Feldbezeichnung ist**. Unter „Geburtsdatum“ fällt das Datum, unter
  „Rechnungsdatum“ oder „Lieferdatum“ nicht. Das ist bewusst die
  vorsichtige Auslegung: Eine Überschrift wie „Name“ über einer beliebigen
  Bemerkung hätte auch schon einmal einen Platzhalter über einen Satz
  gelegt, in dem gar keine Person vorkommt.

### Behoben

- **Eine bereinigte CSV bleibt eine Tabelle.** Die Erkennung liest eine
  CSV-Zeile als Satz und legte ihre Funde deshalb auch schon einmal über
  ein Semikolon hinweg. Der Platzhalter verschluckte das Trennzeichen, die
  Zeile hatte danach eine Spalte weniger, und die Datei ließ sich nicht
  mehr als Tabelle öffnen. Fundstellen enden jetzt an der Zellgrenze, und
  die Anführungszeichen der Maskierung bleiben stehen. Die betroffenen
  Zellen werden anschließend noch einmal für sich gelesen – sonst bliebe
  die Nachbarzelle unbereinigt zurück, die der zu lange Treffer verdeckt
  hatte.

- **Kommentare in Präsentationen.** Die Randbemerkung an einer Folie – oft
  genau die Stelle, an der „Bitte Frau … vor der Sitzung anrufen“ steht –
  blieb unangetastet, samt dem Namen dessen, der sie geschrieben hat. In
  Excel wurde beides längst geräumt; PowerPoint legt Kommentartext und
  Verfasser anders ab, und das war übersehen. Betrifft beide Bauarten: die
  ältere und die, die PowerPoint seit 2019 schreibt – dort auch die
  Dienst-Mailadresse, die am Verfasser hängt. Die Initialen, die
  PowerPoint an der Sprechblase anzeigt, werden mitentfernt.

- **LibreOffice-Dateien: Formel, Benutzerfeld, Notizverfasser.** Was in
  Excel schon geräumt wurde, blieb in der ODS-Tabelle stehen – dort steht die
  Formel nicht als eigenes Element, sondern als Eigenschaft der Zelle, und
  der Name darin überlebte. Beim nächsten Öffnen rechnete LibreOffice ihn
  wieder hin.

  Dazu drei weitere Stellen: Der Wert eines **Benutzerfeldes** steht in
  OpenDocument einmal oben in der Deklaration und wird im Text nur
  abgerufen – ersetzt wurde bisher nur der Abruf, sodass beim Öffnen der
  alte Wert zurückkam. Der **Verfasser einer Notiz** und einer
  nachverfolgten Änderung blieb stehen. Und in einer **Tabelle** wurde die
  Änderungsverfolgung gar nicht ausgeräumt – anders als im Textdokument –,
  sodass gelöschte Zellinhalte samt Bearbeiternamen erhalten blieben.
  Zellbezüge und Summenformeln bleiben dabei unangetastet.

- **Gespeicherte Webseiten geben ihre Attribute preis.** Eine Seite zeigt
  längst nicht alles, was sie enthält. Ein ausgefülltes Formularfeld trägt
  die Eingabe im `value`, eine JavaScript-Oberfläche legt ihren Datensatz in
  `data-…` ab, und der Block für Suchmaschinen (JSON-LD) wiederholt ihn
  vollständig und wohlgeformt: Name, Geburtsdatum, Anschrift, Telefon. Der
  sichtbare Text war bereinigt, all das stand weiter da.

  Jetzt werden auch diese Stellen geräumt, dazu `aria-…` (was dem
  Bildschirmleser vorgelesen wird), `placeholder`, `summary` und der
  vorgeschlagene Dateiname eines Verweises. Der JSON-LD-Block wird dabei als
  Daten gelesen und bleibt gültig – seine Schlüssel und sein Vokabular
  bleiben stehen, nur die Werte gehen. Gewöhnliches JavaScript wird
  weiterhin nicht angerührt.

- **Bilder verlieren ihre Nebendaten auch ohne EXIF.** Ein Foto trägt
  Fotografennamen, Aufnahmezeit und GPS-Koordinaten des Aufnahmeorts
  danebengeschrieben – bei einer Wohnungsanzeige verrät das die Anschrift,
  auch wenn im Text keine steht. Das wurde entfernt, solange das Bild EXIF
  hatte. Waren die Angaben aber **nur** als XMP hinterlegt (so speichern
  Lightroom und Photoshop) oder als Textblock in einem PNG (`Author`,
  `Comment`), blieb das Bild ganz unangetastet. Beides wird jetzt erkannt
  und entfernt – auch bei Bildern, die in einem Dokument stecken und darin
  erhalten bleiben. Die Ausrichtung überlebt weiterhin, und ein Bild ohne
  Nebendaten wird nicht unnötig neu gespeichert.

- **Verweisziele in Tabellen, Präsentationen und Word-Dokumenten.** Wohin
  ein Verweis führt, steht nicht im Text, sondern in einer eigenen Ablage
  der Datei. Eine Mailadresse hinter „Mail schreiben“ überstand deshalb die
  Bereinigung unversehrt, während dieselbe Adresse im Text ersetzt war.
  `mailto:` und `tel:` werden dort jetzt ebenso geräumt wie in gespeicherten
  Webseiten.

### Neu

- **Arztbriefe kommen nicht mehr beschädigt zurück.** Bisher hielt die
  Namenserkennung Arzneistoffe für Personennamen: Aus „Metoprololsuccinat“
  wurde `[NAME]`, aus „Ramipril“ wurde `[ORT]`. Der Medikationsplan war
  danach unbrauchbar – während die Diagnosen unangetastet stehen blieben,
  also genau verkehrt herum. Gemessen betraf das **63 % der Wirkstoffe** und
  **53 % der klinischen Fachbegriffe**, und nicht nur auf Deutsch: über
  sieben Sprachen 74 %, im Italienischen alle geprüften.

  Maskuro kennt jetzt den medizinischen Wortschatz und lässt ihn in Ruhe.
  Übrig bleiben 6 % statt 43 % (deutsch) und 1 % statt 74 % (über die
  Sprachen). Wo eine Anrede davorsteht – „Sehr geehrte Frau …“ – bleibt der
  Name ein Name, auch wenn er zufällig wie ein Arzneistoff heißt.

- **Krankheiten und Medikamente lassen sich entfernen – wenn Sie es wollen.**
  Neuer Haken in den Einstellungen: „Krankheiten und Medikamente ebenfalls
  entfernen“ (Kommandozeile: `--mit-diagnosen`). Für Personalakten,
  Kündigungen und Gutachten, wo die Diagnose niemanden etwas angeht.

  **Voreingestellt aus**, und zwar mit Absicht: Ein Arztbrief *besteht* aus
  Diagnosen und Wirkstoffen. Wer einen anonymisiert – für Forschung, für
  eine Schulung, für ein KI-Werkzeug –, will meistens genau diesen Inhalt
  behalten und nur loswerden, um wen es geht. Die Diagnose ist dort die
  Nutzlast, nicht der Ausweis.

  Die Erkennung findet die gebräuchlichen Bezeichnungen und ersetzt nicht
  die Durchsicht: Eine Krankheitsliste ist nie vollständig, weil der Arzt
  „C2-Abusus“ schreibt, wo die Klassifikation „Störungen durch Alkohol“
  führt.

- **Diagnose- und Arzneischlüssel werden gefunden.** ICD-10 (`I48.2`), ATC
  (`A10BA02`) und die Pharmazentralnummer sind Gesundheitsdaten wie jede
  ausgeschriebene Diagnose – in Entlassbriefen und Abrechnungsunterlagen
  sogar die häufigere Form. Sie sind voreingestellt an, wie die übrigen
  besonderen Kategorien nach Art. 9 DSGVO.

  Ein Diagnoseschlüssel wird nur mit Beleg erkannt: mit „ICD“ davor oder in
  Klammern hinter der Diagnosezeile. Ohne diese Bedingung hielte das
  Programm die Funktionstaste **F10** für eine Suchtdiagnose – in der
  Klassifikation ist F10 genau das.

- **Die fertige Datei lässt sich jetzt kopieren.** An jeder fertigen Zeile
  steht neben „Ansehen“, „Nachbessern“ und „Im Ordner zeigen“ ein vierter
  Knopf: **Kopieren**. Er legt die bereinigte Datei in die Zwischenablage –
  von dort geht sie mit Strg+V (Mac: ⌘V) in eine Mail, ein Chatfenster oder
  ein KI-Werkzeug, ohne den Umweg über den Ordner.

  Kopiert wird die **Datei**, nicht ihr Text: Seitenaufbau, Bilder und die
  Schwärzungsbalken bleiben damit erhalten. Über das Kontextmenü der Liste
  gehen auch mehrere ausgewählte Ergebnisse auf einmal in die
  Zwischenablage, und im Menü „Datei“ steht derselbe Weg als **„Ergebnis
  kopieren“** für alle, die lieber die Tastatur benutzen.

- **Die Länderauswahl kann jetzt dem Dokument folgen.** Ausweis-, Sozial-
  und Steuernummern sind von Land zu Land verschieden, und welche Länder
  geprüft werden, stand bisher für die ganze Sitzung fest – abgeleitet aus
  der Sprache der Oberfläche. Wer deutsch arbeitet und ein französisches
  Schreiben bereinigt, suchte darin also nach deutschen Steuer-IDs und
  nicht nach der französischen Sozialversicherungsnummer.

  Im Regelfenster steht dafür jetzt **„Selbsttätig nach der Sprache des
  Dokuments“**. Die feste Auswahl bleibt daneben bestehen, und das mit
  Absicht: Die Spracherkennung ist nicht unfehlbar – erkennt sie falsch,
  greift die falsche Länderauswahl. Wer nur Akten eines Landes bearbeitet,
  fährt mit der festen Liste sicherer.

  Unberührt davon bleiben die **deutschen** Muster (Steuer-ID, KFZ,
  Durchwahl): Die hängen an der Sprache, nicht an der Länderauswahl, und
  greifen weiterhin auch dann, wenn ein kurzer deutscher Text als Englisch
  eingestuft wird.

- **Kennwörter, Schlüssel und Anmeldenamen werden jetzt gefunden.** Wer eine
  Fehlermeldung, ein Protokoll oder einen Ausschnitt aus einer
  Konfigurationsdatei in ein KI-Fenster kopiert, hat fast immer einen
  Zugangsschlüssel darin – und der stand bisher unverändert da.

  Erkannt wird beides: die verbreiteten Schlüsselformen, die für sich
  sprechen (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token, der
  Kopf eines privaten Schlüssels), und die beschriftete Form – „Passwort:",
  „API-Key =", „Token:", „Benutzername:". Ersetzt wird dabei nur der Wert,
  nie die Beschriftung: „Passwort: [ZUGANGSDATEN_1]" bleibt lesbar, und wer
  das Ergebnis prüft, sieht, dass dort ein Kennwort stand.

  Anmeldename und Kennwort sind zwei getrennte Arten. Wer nur Kennwörter
  entfernen will, schaltet die eine ab und behält die andere.

- **Strich- und QR-Codes in Bildern werden unkenntlich gemacht.** Auf einem
  gescannten Bescheid klebt fast immer ein Code, und darin steht das
  Aktenzeichen – dieselbe Nummer, die im Text daneben entfernt wird. Bisher
  blieb die maschinenlesbare Fassung stehen: Der Balken über der Nummer
  nützt nichts, wenn zwei Zentimeter weiter ein Gerät sie in einer Sekunde
  ausliest.

  Erkannt werden QR-Code, Data Matrix, Aztec, Code 128, EAN und die übrigen
  gängigen Formen. Unkenntlich heißt verpixeln, und zwar gröber als bei
  Gesichtern: Die Fehlerkorrektur eines Codes holt aus wenigen erhaltenen
  Feldern erstaunlich viel zurück, ein halbherziger Schleier wäre keine
  Entfernung.

  Die Option steht neben „Gesichter unkenntlich machen“ und ist ebenso
  **vorbelegt**. Auch bei ausgeschalteter Option sagt der Bericht, wie viele
  Bilder einen Code tragen – ein Gesicht sieht man beim Durchblättern, einen
  Code hält man für Beiwerk.

- **Kartenprüfnummer, PIN und Ablaufdatum werden gefunden.** Die
  Kreditkartennummer fand das Programm schon; erst mit den drei Angaben
  daneben ist sie benutzbar, und auf jedem Abrechnungsbeleg stehen sie
  beieinander. Alle drei nur hinter ihrer Beschriftung – „123“ allein ist
  eine Hausnummer, eine Seitenzahl oder eine Stückzahl.

- **Koordinaten im Text werden gefunden.** Aus Bildern hat Maskuro den
  Aufnahmeort schon bisher entfernt; stand dieselbe Angabe als Text im
  Gutachten oder im Einsatzbericht, blieb sie stehen. Erkannt werden
  Dezimalgrad und die Grad-Minuten-Sekunden-Schreibweise. Bei Dezimalgrad
  muss ein Wort wie „Standort“, „Fundort“ oder „Koordinaten“ in der Nähe
  stehen – sonst wäre jede Messreihe mit zwei Nachkommazahlen eine
  Ortsangabe.

- **Geldbeträge lassen sich jetzt mitentfernen.** Neuer Haken „Geldbeträge
  ebenfalls entfernen“, voreingestellt **aus** wie die Datumsangaben
  darüber: In einem Vertrag ist der Betrag der Inhalt, und wer alles
  schwärzt, schützt niemanden. In einer Gehaltsabrechnung, einem
  Vergleichsvorschlag oder einem Kontoauszug ist er dagegen genau die
  Angabe, die mehr über die Person sagt als der Name daneben — das weiß nur,
  wer das Schriftstück vor sich hat.

  Erkannt wird ein Betrag **nur mit Währungsangabe**: „4.250,00“ allein ist
  eine Stückzahl, erst „4.250,00 EUR“ ist Geld. Währungssymbol, Kürzel und
  ausgeschriebener Name zählen, davor wie dahinter, samt der Schreibweise
  „990,– CHF“.

- **Die besonderen Kategorien nach Art. 9 DSGVO werden erkannt.**
  Religionsbekenntnis, Gewerkschaftszugehörigkeit, politische Überzeugung,
  Gesundheitsangaben – und daneben die strafrechtlichen Angaben nach
  Art. 10. Das sind die Daten, deren Verarbeitung die Verordnung im
  Grundsatz **verbietet**; sie sind deshalb als einzige neue Gruppe
  voreingestellt **an**. Wer sie behalten will, entscheidet das.

  Erkannt wird die Form, in der sie in der Praxis stehen: das Formularfeld
  auf dem Personalbogen – „Religionsbekenntnis: röm.-kath.",
  „Gewerkschaft: ÖGB", „Grad der Behinderung: 50", „Vorstrafen: keine" –,
  und zwar sowohl mit Doppelpunkt daneben als auch mit der Beschriftung
  darüber, wie ein ausgefülltes Blatt sie liefert.

  **Der Fließtext gehört der KI-Stufe.** „Er engagiert sich seit Jahren in
  der Gewerkschaft" ist dieselbe Angabe, und kein Suchmuster findet sie
  zuverlässig. Die KI-Stufe sucht seit dieser Fassung ausdrücklich auch nach
  diesen Kategorien; wer den Fließtext braucht, schaltet sie zu.

- **Personenmerkmale und Beruf – die Angaben, die auch ohne Namen zeigen,
  wer gemeint ist.** Geschlecht, Familienstand, Körpergröße, Augen- und
  Haarfarbe werden ab dieser Fassung entfernt; Beruf, Funktion und Abteilung
  auf Wunsch, über einen eigenen Haken („Beruf und Abteilung ebenfalls
  entfernen“) oder `--mit-berufen`.

  **Warum das eine an und das andere aus ist:** „Die Leiterin der Abteilung
  Einkauf“ benennt in einem Betrieb genau eine Person, auch wenn der Name
  daneben geschwärzt ist – in einem Gutachten oder einer Kündigung gehört
  das entfernt. Eine Mitarbeiterübersicht *besteht* dagegen aus
  Berufsbezeichnungen; wer sie voreingestellt entfernte, gäbe ein leeres
  Blatt zurück. Welcher Fall vorliegt, weiß nur, wer das Schriftstück vor
  sich hat. Die Merkmale darüber stehen fast nur in Formularfeldern, sind
  selten und tragen nie den Inhalt – sie kosten also nichts.

- **Eine fremde Datei nachprüfen.** „Datei → Datei nachprüfen …“ liest ein
  bereits geschwärztes Dokument gegen und meldet, was noch darinsteht – und
  **an welcher Stelle**: Seite und Zeile, Art und Länge. Für den Fall, dass
  jemand die Arbeit eines anderen prüft: eine Akte von der Kanzlei, eine
  Auskunft von der Behörde, die eigene Ausgangspost vor dem Versand.

  **Der Wert selbst steht nicht im Bericht.** Wer die Stelle aufschlägt,
  sieht ihn ohnehin – und der Bericht darf deshalb gespeichert und
  weitergegeben werden, ohne selbst eine Sammlung personenbezogener Daten zu
  sein.

  **Und der Bericht sagt in jedem Fall, was er nicht sehen konnte.** Bilder
  werden nicht gelesen; bei einem Scan ohne Textebene heißt „keine
  Fundstelle“ *nicht geprüft*, nicht *sauber*. Auf der Kommandozeile trennt
  das der Rückgabewert: `--nachpruefen` liefert 0 für geprüft und sauber,
  4 für Fundstellen und 5 für nicht prüfbar. Damit lässt sich Ausgangspost
  automatisch zurückhalten, statt sie durchzuwinken.

- **Prüfbericht: ein Blatt je Bereinigung.** „Datei → Prüfbericht
  speichern …“ – oder `--pruefbericht <ordner>` auf der Kommandozeile –
  schreibt ein einseitiges PDF (wahlweise CSV oder Text) mit den Angaben zum
  Lauf, den gefundenen Arten samt Anzahl, zwei Kennzahlen und einem
  Prüfvermerk. Für den Aktenordner und für die Aufsicht: Das Prüfprotokoll
  ist der belastbare Nachweis, aber niemand legt eine JSON-Lines-Datei vor.

  **Neu sind dabei zwei Zahlen**, die es bisher nirgends zu sehen gab: die
  *durchschnittliche Konfidenz* – wie sicher die Erkennung bei dem war, was
  sie gefunden hat – und die *Maskierungsrate*, der Anteil ersetzter Zeichen
  am Text. Beide stehen mit ihrer Grenze da: Die Konfidenz sagt **nichts**
  über Übersehenes, und neben ihr steht immer, über wie viele Treffer sie
  überhaupt geht; die Rate zählt Bilder nicht mit und fällt bei einem
  bebilderten Dokument zu hoch aus.

  **Fundwerte stehen nicht auf dem Blatt** – dieselbe Grenze wie beim
  Protokoll und beim Suchlauf. Unten stehen zwei Zeilen, die nicht dasselbe
  sagen: Die Prüfsumme zeigt, dass das Blatt unverändert ist; die
  Protokollzeile – nur bei laufendem Protokoll – verweist auf die
  **unterschriebene** Zeile, die den Lauf belegt. Erst sie weist die
  Herkunft nach.

- **„Wie sicher war das?" – die Kennzahlen am Ergebnis.** Ein Knopf
  „Kennzahlen“ unter dem Ergebnis klappt auf, was bisher nirgends zu sehen
  war: Fundstellen, Wörter und Zeichen, die Verteilung je Art als
  Balkenzeile, dazu die durchschnittliche Konfidenz und die Maskierungsrate.
  Dieselben Zahlen wie im Prüfbericht, nur sofort und ohne Ausdruck.

  **Mit ihrem Vorbehalt in derselben Fläche:** Neben der Konfidenz steht,
  über wie viele Treffer sie geht, und darunter der Satz, dass sie **nichts**
  über Übersehenes aussagt. Eine Prozentzahl ohne diesen Satz liest sich wie
  eine Trefferquote – und wer sie so versteht, ist schlechter dran als ohne
  die Zahl.

  Gerechnet wird erst beim Aufklappen: Der Nenner der Maskierungsrate kostet
  je Datei einen Lesevorgang, und den soll nicht bezahlen, wer die Zahlen gar
  nicht ansieht.

- **Eigene Suchmuster bauen, ohne eines zu schreiben.** Der Reiter „Eigene
  Suchmuster“ führt jetzt in drei Schritten durch die Sache: *Was suchen
  Sie? → Wie sieht so eine Angabe bei Ihnen aus? → Benennen und speichern.*
  Sie tippen ein Beispiel ein – etwa `KD-004711` –, das Programm leitet die
  Regel daraus ab und schreibt in Worten hin, wonach sie sucht. Eine
  Vorschau mit Trefferzähler prüft bei jedem Tastendruck mit.

  **Ein regulärer Ausdruck kommt dabei nicht vor.** Das Können war nie das
  Problem: Eigene Suchmuster gibt es seit langem, nur verlangten sie einen
  Ausdruck wie `\bKD-\d{6}\b`, und den schreibt in einer Kanzlei oder
  Personalabteilung niemand. Wer einen schreiben *will*, klappt den
  Experten-Modus auf.

  **Der Vorlagenkatalog ist neu sortiert:** dreizehn Karten mit Namen,
  Erklärung und Beispielwert, gefiltert über Kategoriemarken – Finanzen,
  Behörden, Kontakt, Personal, Medizin.

  Und wenn das abgeleitete Muster zu weit greift, sagt das Programm es von
  sich aus: Ein Beispiel aus lauter Ziffern trifft jede Jahreszahl und jeden
  Betrag, und wer den Ausdruck nicht lesen kann, könnte das sonst nicht
  bemerken.

- **Sieben Marken statt sechsundfünfzig Häkchen.** Ein neuer Reiter „Was
  gesucht wird“ bündelt alle erkennbaren Arten in sieben Gruppen – Person,
  Kontakt und Ort, Kennungen, Finanzen, Technik, Besondere Kategorien,
  Firmen und Eigenes. Eine Marke schaltet ihre Gruppe, „Alle an“ und „Alle
  aus“ die ganze Liste; darunter bleibt jede Art einzeln anhakbar.

  **Voreingestellt ist alles an, und das bleibt so.** Was hier abgeschaltet
  wird, wird gar nicht erst gesucht – der gröbste Eingriff, den das
  Regelfenster erlaubt, und er wirkt auf jedes Dokument. Deshalb steht unter
  der Liste jederzeit, wie viele Arten aus sind, und gespeichert wird nur
  das Abgeschaltete: Eine neue Art ist damit auch in einer Regeldatei von
  vorgestern an, statt stillschweigend herauszufallen.

- **Einen Rahmen auf alle Seiten übertragen.** Im Nachbessern-Fenster nimmt
  der Knopf **Auf alle Seiten übertragen** den zuletzt gezogenen Rahmen und
  schwärzt dieselbe Stelle auf jeder weiteren Seite – für Briefkopf,
  Fußzeile und Aktenzeichenfeld. Bei einer gescannten Akte mit achtzig
  Seiten macht das aus zwanzig Minuten zwei.

  **„Dieselbe Stelle“ heißt die gleiche *relative* Stelle auf dem Blatt.**
  In einem Stapel aus dem Einzug liegt regelmäßig eine Seite quer, eine
  andere ist A3, eine dritte gedreht; ein absolut übertragenes Rechteck
  landete dort neben dem Briefkopf – und man sähe einen Balken und hielte
  die Sache für erledigt.

  **Geschwärzt wird, nicht ersetzt**, auch wenn der Ausgangsrahmen ein
  Platzhalter war: Unter demselben Rechteck steht auf Seite vierzig etwas
  anderes als auf Seite eins, und ein Platzhalter mit derselben Nummer
  behauptete eine Gleichheit, die es nicht gibt.

- **Ein Vermerk auf dem Schwärzungsbalken.** Im Akteneinsichtsrecht steht
  neben jeder Schwärzung, warum geschwärzt wurde. Das neue Feld **Vermerk
  auf dem Balken** in den Einstellungen – oder `--balkenvermerk` – schreibt
  einen kurzen Text auf jeden Balken: „§ 203 StGB“, „DSGVO“, „vertraulich“.
  Für ein Dokument, das eine Behörde herausgibt, ist das der Unterschied:
  Der Empfänger sieht den Grund, ohne ein Protokoll zu haben, das er ohnehin
  nie bekommt.

  **Voreingestellt leer**, denn der Vermerk ist im herausgegebenen Dokument
  sichtbar und selbst eine Angabe – er sagt dem Empfänger, unter welchem
  Titel etwas zurückgehalten wird. Er wirkt nur beim **Schwärzen**; wo ein
  Platzhalter steht, steht kein Balken. Auf einem Balken, der zu klein für
  lesbaren Text ist, entfällt er – ein unlesbarer Vermerk sieht aus wie ein
  Fehler.

- **Freischalten ohne Internetverbindung – jetzt vollständig.** Im
  Lizenzfenster gab es „Ohne Internet freischalten“ schon länger: oben ein
  Anforderungscode zum Mitnehmen, unten das Feld für die Freischaltung, die
  zurückkommt. Nur konnte sie bislang **niemand ausstellen** – das Werkzeug
  dafür fehlte, und der Code lief ins Leere. Das ist behoben.

  Für Behörden und Kanzleien mit abgeschotteten Rechnern ist das kein
  Sonderfall, sondern der Normalfall – und es ist genau die Zielgruppe, bei
  der die Zusage „Ihre Dokumente verlassen den Rechner nie“ am schwersten
  wiegt. Der Code verrät nichts über Dokumente: Er enthält die
  Lizenzkennung und einen Streuwert des Rechners, sonst nichts.

- **Vom Scanner holen.** „Datei → Vom Scanner holen …“ liest einen Stapel
  direkt ein und legt die Seiten in die Liste – für eine Poststelle der
  Unterschied zwischen zwei Arbeitsschritten und einem. Ein Blatteinzug wird
  bis zur letzten Seite geleert; Gerät, Auflösung und Farbe wählt der
  Systemdialog des Scanners, den Sie ohnehin kennen.

  **Bereinigt wird nicht von selbst.** Sie sehen erst, was hereingekommen
  ist, und drücken dann „Bereinigen“ wie bei jeder anderen Datei – ein Scan,
  der sofort durchläuft, nähme Ihnen den Blick auf einen schief eingezogenen
  Stapel.

  **Das gibt es nur unter Windows**, und der Menüpunkt sagt das auf dem Mac
  auch: Dort schreibt die Software Ihres Scanners in einen Ordner, und
  „Ordner überwachen …“ bereinigt alles, was dort landet.

### Sonstiges

- **Die Liste aller gefundenen Angaben liegt jetzt bei** und wird aus dem
  Quelltext erzeugt (`hilfe/GEFUNDENE-ANGABEN.md`): 177 Arten in 35 Ländern,
  23 davon mit Prüfziffernrechnung. Sie nennt auch, wie gezählt wurde – wir
  zählen `[NAME]` einmal, wo andere Vor-, Zweit- und Nachnamen als drei
  Einträge führen.

- **Schwärzen gibt es jetzt auch in Word, PowerPoint, OpenDocument und
  HTML.** Die Wahl zwischen Platzhalter und Schwärzung stand bisher nur für
  PDF-Dateien. Jetzt können es auch die anderen: Der Fund wird entfernt, und
  an seiner Stelle steht ein schwarzer Balken – im Dokument selbst, nicht als
  Bild darüber. Wer die Datei weiterreicht, gibt eine geschwärzte Akte weiter
  und keine, in der das Geschwärzte noch als Text darunterliegt.

  **Entschieden wird es getrennt**, in zwei Wahlfeldern: „Bei PDF“ und „Bei
  Word, PowerPoint, OpenDocument und HTML“. Man will es verschieden – das
  geschwärzte PDF geht zur Behörde, dieselbe Sache als Word-Datei wandert
  weiter durchs Haus und soll lesbar bleiben. Auf der Kommandozeile
  entsprechend `--pdf-modus` und `--office-modus`; ein gespeichertes
  „Schwärzen“ aus früheren Fassungen gilt weiterhin dem PDF.

  In Tabellen, reinem Text, CSV und E-Mail geht der Balken nicht – dort fehlt
  die Fläche, auf die er sich legen ließe. Es wird weiterhin ein Platzhalter
  eingesetzt, und das Ergebnis **sagt es jetzt**, statt es stillschweigend zu
  tun.

- **Neu: „Entfernen“ – die Fundstelle bleibt einfach leer.** Die dritte
  Betriebsart neben Platzhalter und Schwärzen, und die einzige, die **jedes**
  Format kann: Etwas wegzulassen braucht keine Fläche. Im PDF wird dabei
  nichts gezeichnet, in Word und HTML bleibt die Stelle leer, in einer
  Tabelle ebenso.

  Sie ist die stillste der drei: Wer das Ergebnis liest, sieht nicht, dass
  dort je etwas stand – auch die Länge des Werts verrät sich nicht mehr. Für
  ein Schriftstück, das jemand prüfen soll, bleibt der Platzhalter meist die
  bessere Wahl.

  In Bildern gilt keine der drei Wahlen: Bildpunkte lassen sich nicht durch
  einen Platzhalter ersetzen und nicht weglassen. Was die Texterkennung dort
  findet, wird wie bisher immer übermalt.

- **Das Nachbessern-Fenster behauptet keine Ersetzungen mehr, die es nicht
  gibt.** Rechts stand zu jedem Wert ein Platzhalter – auch bei einer
  geschwärzten Datei, in der kein einziger vorkommt. Ein Klick auf so eine
  Zeile markierte nichts, und „Zurücknehmen“ lief ins Leere. Jetzt steht dort
  „geschwärzt“ bzw. „entfernt“, und die Zeilen lassen sich gar nicht erst
  zurücknehmen: Der Text ist fort, es gibt nichts zurückzuholen. Das galt für
  geschwärzte PDF-Dateien, für Word und OpenDocument und für alles, was in
  Bildern gefunden wurde.

- **Die Textansicht zeigt die Balken jetzt als Balken.** Eine geschwärzte
  Word-Datei sah beim Nachbessern **leer** aus: An den geschwärzten Stellen
  standen Lücken, als hätte das Programm den Text verschluckt. Der Grund war
  die Anzeige, nicht das Ergebnis – im Dokument selbst lag der Balken die
  ganze Zeit richtig. Jetzt steht er auch in der Ansicht dort, schwarz wie im
  Ergebnis, in Word, PowerPoint, OpenDocument und HTML.

- **Outlook-Nachrichten (`.msg`) werden jetzt bereinigt.** `.eml` gab es
  längst – in deutschen Firmen ist Outlook aber die E-Mail, und dort heißt
  eine gespeicherte Nachricht `.msg`. Damit ist das dichteste PII-Format auch
  in seiner verbreitetsten Ablageform abgedeckt: Betreff, Absender,
  Empfängerzeilen, Nachrichtentext, HTML-Fassung, Empfängerliste und
  Anhänge – letztere über die vorhandenen Wege und mit denselben
  Platzhaltern wie der Mailtext.

  **Eine `.msg` trägt denselben Text mehrfach**, und das ist die Falle: als
  Reintext, als HTML **und** als RTF. Wer nur den Reintext bereinigt, hat
  nichts getan – Outlook zeigt bevorzugt das RTF. Die RTF-Fassung wird
  deshalb ganz entfernt, ebenso die Internet-Kopfzeilen mit ihrer
  Received-Kette und die binären Suchschlüssel, die Namen und Adressen
  überstehen jede Textbereinigung. Das Ergebnis öffnet sich weiterhin in
  Outlook und zeigt den Text ohne Schriftauszeichnung; der Bericht sagt das
  ausdrücklich.

- **Regeln in eigenen Worten beschreiben, statt Regex zu schreiben.** Das
  Regeln-Fenster kann viel und verlangte dafür ein reguläres
  Ausdrucksmuster – die Stelle, an der es für die meisten aufhört. Jetzt
  genügt ein Satz: „Unsere Aktenzeichen der Form 12 C 345/26 sollen stehen
  bleiben.“ Die KI-Stufe schlägt daraus Begriffe und Suchmuster vor.

  **Übernommen wird nur, was Sie anhaken – und voreingestellt ist nichts
  angehakt.** Zu jedem Vorschlag steht ein Satz, was er bedeutet, und die
  Zahl seiner Treffer in einem Beispieltext, den Sie mitgeben können. Was
  Schutz **wegnimmt**, ist als solches gekennzeichnet: „diesen Begriff immer
  entfernen“ und „diesen Begriff nie entfernen“ sähen in einer Liste sonst
  gleich aus. Vorschläge, die auf alles passen würden, werden gar nicht erst
  gezeigt.

- **Das Prüfprotokoll zählt jetzt über alle Arbeitsplätze zusammen.** Legt
  ein Haus die Protokolle über `protokoll_pfad` auf eine Freigabe, schreibt
  dort jeder Arbeitsplatz seine eigene Monatsdatei – bisher musste ein
  Datenschutzbeauftragter mit dreißig Plätzen dreißig Dateien einzeln
  ansehen. Über der Liste steht jetzt eine Zeile mit den Summen des Monats,
  und **sie meldet gebrochene Ketten mit Namen**: Eine nachträgliche Änderung
  fällt nur auf, wenn jemand nachsieht, und in dreißig Dateien sieht niemand
  von Hand nach.

  **Keine Aufstellung je Person** – auch nicht in dieser Ansicht. Eine
  Rangfolge „wer hat wie viel bereinigt“ wäre zur Verhaltens- und
  Leistungskontrolle geeignet, und darauf kommt es mitbestimmungsrechtlich
  an, nicht auf die Absicht. Gezählt werden Läufe, Dateien und Treffer über
  das Haus.

- **„Profil aus einem Schriftstück vorschlagen": die Regeln einmal fragen
  statt vierundvierzig Arten durchgehen.** Im Regeln-Fenster gibt es einen
  neuen Knopf: Er zeigt der KI-Stufe ein Schriftstück, bestimmt, worum es
  sich handelt – Arztbrief, Bewerbung, Vertrag, Rechnung, Bescheid – und
  schlägt die Strategien vor, die dazu passen. Beim Arztbrief etwa werden
  Datumsangaben verschoben statt ersetzt, weil in einer Krankenakte die
  Chronologie der Inhalt ist.

  **Die Profile stehen im Programm, das Modell wählt nur aus** – die
  Schwärzungsregeln hängen nicht davon ab, was ein Sprachmodell für eine gute
  Idee hält. Vorgeschlagen wird jeder Punkt einzeln und mit Begründung;
  übernommen wird nichts ohne Rückfrage, und was Sie selbst festgelegt haben,
  bleibt unangetastet. Ohne KI-Stufe bleibt es bei der sicheren Vorgabe:
  Platzhalter für alles.

- **Neue Strategie „erfinden": ein plausibler Falschwert statt eines
  Platzhalters.** „Frau Berger schrieb an Herrn Doppler in Fulda“ statt
  „[NAME_1] schrieb an [NAME_2] in [ORT_1]“ – für Schulungsunterlagen,
  Vorführakten, Testdatenbestände und alles, was anschließend einer KI
  vorgelegt wird. Anrede, Satzbau und Lesbarkeit bleiben erhalten.

  Derselbe Wert bekommt denselben Falschwert, über alle Dateien eines
  Vorgangs hinweg und auf jedem Rechner mit derselben Regeldatei – **ohne
  dass irgendwo eine Zuordnung gespeichert wird** (dieselbe Mechanik wie beim
  Hashen). E-Mail-Adressen liegen auf reservierten Beispiel-Domänen,
  Telefonnummern im dafür freigehaltenen Bereich, erfundene IBANs tragen eine
  richtig gerechnete Prüfziffer. Möglich für Namen, Orte, Adressen, Firmen,
  E-Mail, Telefon und IBAN; für andere Arten wird die Regel abgelehnt, statt
  wirkungslos zu bleiben.

  **Der Bericht sagt ausdrücklich, dass erfunden wurde.** Ein so bereinigtes
  Dokument liest sich wie ein echtes und ist keines – es taugt nicht als
  Nachweis und darf nicht als Original weitergegeben werden.

- **Die Gegenprobe: „Wer bleibt erkennbar?"** Ein neuer Haken unter der
  KI-Stufe legt das **fertige Ergebnis** noch einmal dem Sprachmodell vor und
  fragt, wer trotz Bereinigung zu erkennen ist. Gemeint ist der Fall, den
  keine Erkennung der Welt findet, weil dort gar kein Name steht: „die
  einzige Hebamme im Bezirk“, „der Kollege, der im März nach dem Brand
  gekündigt hat“. Kein Muster greift, und vor Ort weiß trotzdem jeder, wer
  gemeint ist.

  **Es wird dabei nichts entfernt.** Die Stellen stehen mit einem Satz
  Begründung im Bericht, und entschieden wird von Hand – ein Programm, das
  von sich aus Sätze aus einem Schriftstück nimmt, weil sie ihm verräterisch
  vorkommen, macht aus einer Bereinigung eine Umschreibung, und niemand sähe,
  was fehlt. Höchstens fünf Stellen je Datei; was das Modell nicht wörtlich
  belegen kann, fällt weg. In der Kommandozeile: `--restrisiko` zusammen mit
  `--ki`.

- **Der Weg zurück aus der KI: „Antwort zurückübersetzen“.** Bisher war nur
  die halbe Schleife gebaut – Text kopieren, bereinigt einfügen, der KI
  vorlegen. Die Antwort kam mit `[NAME_1]` zurück, und wer sie brauchen
  konnte, setzte von Hand wieder ein, was er von Hand herausgenommen hatte.
  Jetzt steht der Rückweg im Menü „Programm“: Antwort kopieren, Eintrag
  anklicken, die echten Namen stehen wieder da.

  Die Zuordnung dafür liegt **nur im Arbeitsspeicher**, gilt immer nur für
  die zuletzt bereinigte Stelle und läuft nach einer Stunde ab; wer den
  Zwischenablage-Wächter abschaltet, wird sie sofort los. Zurückholen lässt
  sich dabei nur, was ersetzt wurde – Geschwärztes, Maskiertes und Gehashtes
  ist nicht umkehrbar, und das Programm sagt, wie viele Stellen es deshalb
  stehen lassen musste. Verwaltete Installationen schalten den Rückweg über
  die Vorgabe `rueckweg` ganz ab.

- **Ordner überwachen: was hineingelegt wird, liegt kurz darauf bereinigt im
  Ausgang.** Für eine Poststelle, ein Postfach-Team oder einen Scan-Ordner –
  einmal einrichten, danach klickt niemand mehr. Zu finden unter
  „Datei → Ordner überwachen …“, in der Kommandozeile über `--wache <ordner>`.

  Das Original bleibt liegen, wo es lag; auf Wunsch wandert es unverändert in
  den Unterordner „Erledigt“, wobei nie etwas überschrieben wird. Angefasst
  wird eine Datei erst, wenn sie fertig geschrieben ist – eine noch über das
  Netz kopierte Datei würde sonst halb gelesen und als bereinigt gemeldet.
  Was schiefgeht, bleibt liegen und wird gesagt, statt endlos wiederholt zu
  werden. Und die Wache merkt sich Erledigtes ohne Dateinamen: Was in einem
  Eingangsordner liegt, verrät oft schon im Namen, worum es geht.

  **Die Überwachung eines Ordners außerhalb des eigenen Benutzerprofils –
  etwa auf einem Netzlaufwerk – setzt eine Automatisierungslizenz voraus.**
  Ein Ordner, den mehrere Menschen erreichen, ist ein Dienst und kein
  Arbeitsplatz; im eigenen Profil und während des Testzeitraums gilt die
  Einschränkung nicht.

### Behoben

- **Die Einstellungen waren rechts abgeschnitten.** Das Fenster ging mit
  einer festen Größe auf, und die reichte nur für die Schriftgröße, mit der
  entwickelt wurde: Auf dem Mac standen „Jetzt prüfen“, „Ändern …“ und die
  Hinweise daneben zur Hälfte außerhalb. Jetzt öffnet es so breit, wie seine
  Seiten es brauchen – in jeder Sprache und bei jeder Schriftgröße, begrenzt
  nur durch den Bildschirm.

- **„Jetzt prüfen“ antwortet jetzt sichtbar.** Das Ergebnis stand in der
  Statuszeile des Hauptfensters – also hinter dem Einstellungsfenster, aus
  dem heraus gefragt wurde. Wer prüfte, sah nichts. Jetzt kommt die Antwort
  als Meldung über den Einstellungen, und liegt eine neue Fassung vor, führt
  sie gleich zum Installieren. Beim Programmstart bleibt es wie bisher bei
  der Statuszeile, ungefragt geht kein Fenster auf.

- **Kopierte Dateien kamen auf dem Mac nicht in der Zwischenablage an.** Das
  Zurücklegen bereinigter Dateien meldete Erfolg und legte doch nichts
  Brauchbares ab – Einfügen ergab nichts. Betroffen war alles, was Dateien
  in die Zwischenablage schreibt.

- **Und aus der Zwischenablage wurde auf dem Mac nur die erste Datei
  gelesen.** Wer drei Dateien im Finder kopierte und „Zwischenablage jetzt
  bereinigen“ wählte, bekam zwei davon unbereinigt zurück – ohne dass
  irgendetwas das gesagt hätte. Jetzt kommen alle.

- **„Datei nachprüfen“ nimmt jetzt auch gezogene Dateien an** – wie das
  Hauptfenster. Abgelegtes kommt dazu, statt die bisherige Auswahl zu
  verwerfen; dasselbe zweimal abzulegen ändert nichts, und was das Programm
  nicht lesen kann, wird gesagt statt verschluckt.

- **Und das Fenster sagt, dass es auf Sie wartet.** Es ging mit einem
  leeren Kasten auf und einem grauen Knopf „Nachprüfen“ – das sieht aus,
  als sei nichts da, nicht als fehle die Auswahl. Jetzt steht dort „Noch
  keine Datei gewählt – hierher ziehen oder unten über ‚Dateien auswählen
  …‘ aussuchen.“

- **Ein langer Lauf sagt jetzt, dass er läuft.** „Zusatzmodell für die
  genauere Erkennung wird geladen – einen Moment …“ blieb stehen, solange
  die Erkennung rechnete: bei einer Datei mit 47 500 Wörtern also
  achtzehn Minuten, obwohl das Laden nach neun Sekunden vorbei war. Wer
  das sieht, hält das Programm für hängen geblieben. Jetzt folgt darauf
  „Genauere Erkennung läuft – das dauert bei langen Texten einige
  Minuten“, und die Statuszeile zählt mit: „Genauere Erkennung (7/312)“.
  Gemeldet wird dabei aus der Schleife des Modells – alle 250 Wörter, also
  rund alle sechs Sekunden –, nicht je Textblock: Ein Textblock trägt
  zwölftausend Wörter und braucht Minuten.

- **Ein abgebrochener Lauf sagt jetzt, dass er abgebrochen wurde.** Wer
  „Abbrechen“ drückte, las danach „0 von 1 Datei(en) bereinigt.“ – richtig
  gezählt und trotzdem die falsche Auskunft. Die Meldung, welche Datei es
  traf, wurde im selben Augenblick von der Zählmeldung überschrieben. Und
  in der Dateiliste stand weiter „läuft …“, obwohl nichts mehr lief; dort
  steht jetzt „abgebrochen“.

- **Der Satz über den Datenschutz war abgeschnitten.** „… keine Cloud, kein
  Hochladen. Mehr im Datens“ – bei der Fensterbreite, mit der das Programm
  startet, endete er mitten im Wort. Er nimmt jetzt die volle Breite.

- **Der Lizenzdienst konnte etwas mitteilen, und niemand hörte zu.** Wenn
  alle Lizenzplätze belegt sind, die Lizenz abgelaufen ist, der Schlüssel
  unbekannt oder die Lizenzverwaltung beim Anbieter abgeschaltet, schickt der
  Dienst genau dafür einen Grund – vorgesehen war von Anfang an, dass Sie ihn
  **einmal** erklärt bekommen. Gezeigt wurde er nie. Jetzt erscheint ein
  Hinweis, der zuerst sagt, dass das Programm unverändert weiterarbeitet, und
  dann, worum es geht. Einmal je Grund: Wer ihn weggeklickt hat, sieht ihn
  bei der täglichen Prüfung nicht wieder – wohl aber, wenn sich der Grund
  ändert.

- **Eine im Shop gekaufte Mehrplatzlizenz zeigte „1 Platz".** Der Shop
  verteilt vorbereitete Schlüssel und hält die gekaufte Platzzahl bei sich;
  angezeigt wurde aber die Zahl aus dem Schlüssel selbst, und die lautet bei
  jedem Vorratsschlüssel auf einen Platz. Wer acht Plätze gekauft hatte, las
  „1 Platz“ – und ab dem zweiten angemeldeten Rechner stand die Anzeige in
  Rot samt „Bitte an Ihre Verwaltung“. Jetzt gilt die Zahl, die der Dienst
  zuletzt gemeldet hat; ohne Antwort bleibt es beim Schlüssel, und kleiner
  als der gekaufte Umfang wird es nie. Dasselbe gilt für Nachkäufe und
  Verlängerungen: Die ändern beim Anbieter die Platzzahl, nicht Ihren
  Schlüssel.

- **Nach dem Kauf stand „Lizenziert für Maskuro Privatlizenz“.** Das ist kein
  Name, sondern der Platzhalter, unter dem die Schlüssel vorbereitet werden –
  Ihr Name kann dort nicht stehen, weil der Schlüssel schon vor dem Kauf
  unterschrieben wird. Statt Ihnen einen fremden Namen als Ihren zu zeigen,
  steht dort jetzt schlicht „Privatlizenz“ und die Platzzahl. Bei einer
  Lizenz, die auf Sie ausgestellt wurde, steht Ihr Name unverändert dort.

- **Im Hilfe-Menü stand „Hilfe _FAQ“.** Das Und-Zeichen war zu einem
  Unterstrich geworden, weil Qt es als Kennzeichen für einen
  Tastaturbuchstaben las. Jetzt steht dort „Hilfe & FAQ“.

- **Das Einstellungsfenster blieb stehen, wenn das Programm ins Symbol
  verschwand** – und auch dann noch, wenn das Hauptfenster geschlossen
  wurde. Es geht jetzt mit. (Betrifft nur diese Fassung; das eigene
  Fenster ist neu.)

- **Eine abgelehnte Lizenzanfrage sagt jetzt, woran es liegt.** Wies der
  Lizenzdienst eine Anfrage ab, ohne einen Grund mitzuschicken, stand im
  Lizenzfenster in Rot „Unbekannte Antwort.“ – ein Satz, mit dem weder Sie
  noch der Support etwas anfangen können und der Sie den Fehler bei Ihrem
  Schlüssel suchen lässt. Jetzt steht dort, was tatsächlich geschah: dass
  der Dienst abgelehnt hat, ohne es zu begründen, und an wen Sie sich
  wenden. Ist die Lizenzverwaltung beim Anbieter vorübergehend
  abgeschaltet, wird auch das benannt – samt dem Hinweis, dass Ihr
  Schlüssel davon nicht betroffen ist.

- **Auf dem Mac galten eingerichtete Sprachen plötzlich als fehlend.** Beim
  Start meldete das Programm „Es ist kein Sprachmodell installiert“ und bot
  die Ersteinrichtung an, obwohl die Sprachen längst geladen waren – wer
  unter „Sprachen der Dokumente“ nachsah, fand sie dort vollzählig. Das
  Programm suchte sie je nach Startweg an zwei verschiedenen Orten: Wurde es
  aus dem Programme-Ordner gestartet, fand es sie; wurde derselbe Bau als
  einfacher Ordner gestartet, suchte es sie neben sich, wo keine liegen. Ab
  jetzt gilt auf dem Mac ausnahmslos derselbe Ort im Benutzerprofil, gleich
  wie das Programm verpackt ist. Nichts muss neu geladen werden.

- **„Was ist neu“ zeigte die halbe Liste.** Das Fenster nach einer
  Aktualisierung brach mitten im Satz ab, und die restlichen Punkte standen
  als leere Aufzählungszeichen da. Schuld war ein Platzhalter in spitzen
  Klammern – etwa `<datei>.docx` –, den die Anzeige für Auszeichnung
  hielt und ab dem alles Weitere verwarf. Ausgerechnet die Neuerungen zur
  Sicherheit waren davon betroffen. Die Hilfe zeigt solche Platzhalter seit
  jeher richtig; dieses Fenster tut es jetzt auch.

- **Kneifen mit zwei Fingern zoomt jetzt im Nachbessern-Fenster.** Auf dem
  Trackpad ist das *die* Zoomgeste – im Editor tat sie bisher nichts, und wer
  eine Stelle genauer ansehen wollte, musste zum Regler oder zu Strg+Mausrad
  greifen. Die Seite folgt der Geste unmittelbar und wird beim Loslassen
  wieder scharf gezeichnet.

- **Gezoomt wird auf die Stelle, die man ansieht.** Kneifen vergrößert um den
  Punkt zwischen den Fingern, Strg+Mausrad um den Punkt unter dem Zeiger.
  Knöpfe, Tastenkürzel und der Zoomregler halten die Mitte fest – zu ihnen
  gehört keine Stelle, auf die man zeigt. Vorher blieb bei allen nur der
  Rollwert stehen: Von einer eingepassten Seite aus hielt das die Oberkante,
  und alles darunter wanderte beim Hineinzoomen aus dem Bild.

- **„Vorher/Nachher“ war in der Seitenansicht ein toter Knopf.** Solange die
  Seitenansicht an war, ließ er sich drücken – und meldete jedes Mal, das
  Original sei nicht zu öffnen. Zu vergleichen gibt es dort auch nichts: Die
  Seitenansicht ist ein Abbild der bereinigten Fassung, ein Gegenstück zum
  Original gibt es nicht. Der Knopf ist jetzt gesperrt und nennt beim
  Darüberfahren den Grund samt Ausweg (die Textansicht). Seine Beschreibung
  versprach obendrein ausdrücklich, der Vergleich gehe „unabhängig davon, ob
  Text- oder Seitenansicht aktiv ist“ – das stimmte nie.

- **Die Seitenansicht ließ LibreOffice abstürzen.** Wurden zwei
  Seitenansichten gleichzeitig erzeugt – etwa „Als PDF schwärzen“ während die
  Vorschau noch rechnete –, meldete sich das System mit einem
  LibreOffice-Absturz, obwohl die Seiten am Ende doch erschienen: Beide Läufe
  griffen auf dieselbe Arbeitsablage von LibreOffice zu, was es nicht
  verträgt. Jetzt bekommt sie immer nur ein Lauf; die übrigen weichen auf eine
  eigene aus. Sie brauchen dafür ein paar Sekunden länger, dafür kommt keine
  Fehlermeldung mehr, und keiner der Läufe bleibt ohne Ergebnis. Ein zweiter
  Renderauftrag neben einem laufenden wird außerdem gar nicht erst
  angenommen.

- **„Original zeigen“ konnte das Programm beenden.** Ließ sich das Original
  nicht öffnen – weil es verschoben, umbenannt, mit einem Kennwort versehen
  oder auf einem getrennten Laufwerk liegt –, brach das Nachbessern-Fenster
  ohne Vorwarnung ab, und offene Arbeitskopien waren verloren. Jetzt kommt
  ein Hinweis, der Schalter springt zurück, und die bereinigte Fassung bleibt
  stehen. Wo das Original grundsätzlich nicht danebenpasst – etwa bei einer
  PDF-Seitenansicht, die aus einer Word-Datei entstanden ist –, ist der
  Schalter von vornherein gesperrt und nennt beim Darüberfahren den Grund,
  statt bei jedem Druck denselben Hinweis zu zeigen.

- **Fehlerberichte kamen nie an.** Wer einen Fehler melden wollte, bekam „Die
  Gegenstelle hat den Bericht abgelehnt“ – und niemand hatte ihn je gesehen.
  Zwei Ursachen, beide auf dem Weg: Das Programm wies sich beim Server nicht
  aus und wurde deshalb vom Schutz vor Massenzugriffen abgewiesen, und die
  Adresse verwies auf einen zweiten Namen, dem das Programm nicht folgte.
  Beides ist behoben; ein Bericht geht wieder hinaus. **Dasselbe traf die
  Lizenzfreischaltung**: Anmelden, Abmelden und Nachfragen erreichten den
  Dienst ebenfalls nicht – dort nur unauffällig, weil eine unbeantwortete
  Anfrage bewusst nichts an Ihrer Lizenz ändert. Und bleibt eine Absage doch
  einmal unerklärlich, steht jetzt ihre technische Nummer dabei, statt dass
  jede Ursache gleich aussieht.

- **Ein Klick auf „Original zeigen“ konnte das Programm beenden.** Ließ sich
  das Original nicht öffnen – verschoben, umbenannt, auf einem getrennten
  Netzlaufwerk, mit einem Kennwort versehen oder beschädigt –, verschwand das
  Nachbessern-Fenster mitsamt allen offenen Arbeitskopien. Jetzt bleibt der
  Umschalter bei der bereinigten Fassung, und ein Kasten sagt, was los ist;
  der technische Grund steht in den Details, falls Sie ihn melden möchten.
  Dasselbe gilt für ein Ergebnis, das sich nicht anzeigen lässt: Das Fenster
  geht auf und sagt es, statt zu verschwinden.

- **Die Frage nach einem Absturz kam zu oft – und löschte die Spur, nach der
  sie fragte.** Sie erschien auch dann, wenn nichts abgestürzt war: Der
  Vermerk entsteht, sobald irgendwo eine unerwartete Störung auftritt, auch
  wenn das Programm sie übersteht und danach ganz gewöhnlich beendet wird;
  weggeräumt wurde er nie. Und wer „Nein“ antwortete, vernichtete die
  einzigen Einzelheiten des Vorfalls – der Vermerk verschwand schon beim
  *Anzeigen* der Frage. Beides ist behoben: Ein geordnetes Ende räumt den
  Vermerk weg, gefragt wird nur noch nach einem echten Abbruch, und abgehakt
  wird erst nach Ihrer Antwort. Die Einzelheiten stehen ohnehin im
  Fehlerprotokoll auf dem eigenen Rechner – wer nichts senden will, verliert
  damit trotzdem nichts. Gesendet wird nach wie vor nur, was Sie vorher
  vollständig gesehen und selbst freigegeben haben.

- **„Bereinigen“ konnte stumm gesperrt bleiben.** Bleiben die Sprachmodelle
  beim Laden hängen, blieb der Knopf abgeschaltet – ohne Erklärung. Ein Klick
  darauf tat nichts, und die Statuszeile sagte unverändert „Sprachmodelle
  werden geladen …“, auch nach zehn Minuten. Die Ursache: Störungen in
  Hintergrundabläufen gingen an eine Stelle, die beim Start aus dem
  Dateimanager niemand sieht; zurück blieb ein Fenster, das arbeitsbereit
  aussah und auf keinen Klick reagierte. Jetzt landen solche Störungen im
  Fehlerprotokoll, das Laden der Sprachmodelle meldet sein Scheitern in jedem
  Fall statt still aufzugeben, und bleibt es trotzdem still, sagt die
  Anwendung nach einer Dreiviertelminute, dass etwas nicht stimmt, mit einem
  Rat in den Details. Der gesperrte Knopf nennt beim Darüberfahren seinen
  Grund. Ein langes erstes Nachladen gilt dabei nicht als Stille – solange
  Fortschritt gemeldet wird, bleibt es ruhig. Als Absturz zählt das alles
  nicht: Die Anwendung läuft weiter, und beim nächsten Start wird deshalb
  auch nicht danach gefragt.

- **Auf dem Mac fand das Programm keine Aktualisierungen mehr – und sagte,
  es sei auf dem neuesten Stand.** Die Mac-Fassung brachte kein Verzeichnis
  der Wurzelzertifikate mit; sie suchte es an einer Stelle, die es nur auf
  dem Rechner gibt, auf dem sie gebaut wird. Damit konnte sie bei keinem
  Server prüfen, mit wem sie spricht, und brach jede Verbindung ab: keine
  Aktualisierungen, keine Lizenzfreischaltung, kein Nachladen von
  Sprachmodellen, kein Fehlerbericht. Ältere Fassungen machten daraus
  stillschweigend die Auskunft „Sie verwenden die neueste Fassung“. Die
  Zertifikate liegen jetzt im Programm selbst; findet es dort keine, nimmt
  es die des Systems und auf dem Mac notfalls die des Schlüsselbunds – und
  wenn es gar keine gibt, sagt es das, statt eine neueste Fassung zu
  behaupten. Die Prüfung selbst wird dabei nie abgeschaltet.

  Diese eine Aktualisierung müssen Mac-Anwender noch von Hand installieren:
  Eine Fassung, die den Server nicht erreicht, kann sich auch nicht selbst
  erneuern.

### Geändert

- **Das Hauptfenster ist aufgeräumt worden.** Unten standen sechs
  gleich große Knöpfe nebeneinander – „Über …“, „Anleitung“ und „Hilfe &
  FAQ“ darunter, obwohl dieselben drei Wege im Hilfe-Menü darüber schon
  standen. Sie sind jetzt zu einem Knopf „Hilfe“ zusammengefasst, der sie
  aufklappt; verloren geht keiner. Übrig bleiben unten die beiden Wege, mit
  denen man wirklich anfängt: „Bereinigen“ und „Von Hand schwärzen …“.

- **Was das Programm gerade tut, steht jetzt an einem festen Ort.** Die
  Meldung („Sprachmodelle werden geladen …“, „(3 / 7) brief.pdf“, „5 von 7
  Datei(en) bereinigt.“) hing bisher als grauer Text zwischen zwei
  Knopfreihen. Sie hat eine eigene Fläche bekommen, mit einem farbigen
  Punkt davor: grau, solange nichts läuft, blau während der Arbeit, grün
  nach einem glatten Lauf und gelb, wenn Hinweise angefallen sind. Der
  Punkt sagt nichts, was nicht daneben steht – er sagt es nur schneller.

- **Die Einstellungen sind ein eigenes Fenster geworden.** Sie lagen
  bisher im Hauptfenster – ein Kasten mit vier Reitern, den man unter
  „Mehr Einstellungen“ aufklappte, und der dann für seinen Inhalt zu klein
  war: Es stand immer ein Rollbalken darin, und die Wahl zwischen
  Anonymisieren und Pseudonymisieren stand halb im Bild. Der Knopf heißt
  jetzt „Einstellungen …“ und öffnet ein Fenster mit einer Seitenleiste;
  jede der vier Seiten passt ganz hinein. Das Hauptfenster springt beim
  Öffnen nicht mehr auf, und man kann die Dateiliste nebenher sehen.
  Geändert hat sich nur, wo die Einstellungen stehen – welche es gibt und
  was sie tun, ist unverändert.

- **„Details“ klappt auf, statt zu springen.** Das Fenster wuchs bisher
  in einem Bild, und man musste danach suchen, was sich geändert hatte.
  Jetzt bewegt es sich dorthin.

- **Schriftgrößen und Abstände folgen im ganzen Fenster demselben Maß.**
  Überschriften waren an zwei Stellen verschieden groß, und gleichrangige
  Zeilen standen unterschiedlich weit auseinander. Sichtbar ist das als
  Ruhe, nicht als einzelne Änderung.

- **Anonymisieren ist jetzt die Vorgabe.** Bisher war das Pseudonymisieren
  voreingestellt: Gleiche Personen bekamen dieselbe Nummer (`[NAME_1]`,
  `[NAME_2]`), Bezüge blieben lesbar – rechtlich blieben es damit aber
  **personenbezogene Daten**. Wer nichts einstellt, bekommt jetzt das
  Verfahren, das die Daten aus der DSGVO herausnimmt: Alle Treffer einer Art
  heißen gleich (`[NAME]`). Die Nummerierung ist eine Wahl geblieben, sie
  steht unverändert im selben Fenster; bestehende Einstellungen bleiben, wie
  sie sind. Auf der Kommandozeile stellt `--pseudonymisieren` (auch
  `--mit-nummerierung`) zurück.

- **Anonymisierte Platzhalter lassen sich nicht mehr einzeln zurücknehmen.**
  Wer anonymisiert, bekommt für jede Person denselben Platzhalter – und damit
  gibt es keine einzelne Stelle mehr, die zu einem bestimmten Namen gehört.
  Das Nachbessern-Fenster bot trotzdem „Ersetzung zurücknehmen“ an: Ein Klick
  hätte *einen* der Werte an *allen* Stellen eingesetzt. Die Zeilen sind
  jetzt gedämpft wie bei geschwärzten Angaben, der Klick sagt den Grund, und
  ein von Hand nachgezogener Fund bekommt keine Nummer mehr, die im übrigen
  Dokument nirgends steht.

  Aus demselben Grund gibt es nach einem anonymisierten Lauf kein
  „Antwort zurückübersetzen“ mehr – vorher hätte es einen fremden Namen an
  die Stelle jeder Person gesetzt. Wer diese Schleife braucht, wählt
  „Pseudonymisieren“; die Anwendung sagt das jetzt auch so, statt auf eine
  abgelaufene Zuordnung zu verweisen.

  Auf der Kommandozeile bricht `--zuordnung` beim Anonymisieren jetzt ab,
  statt eine Datei zu schreiben, die keine Rückübersetzung ist – im Fenster
  war der Haken längst gesperrt. Entweder `--pseudonymisieren` dazu oder
  `--zuordnung` weglassen; die Meldung sagt es. Das Ergebnis entsteht dabei
  gar nicht erst, damit ein Skript nicht mit halber Arbeit dasteht.

- **Der Aktualisierungskanal steht neu auf „Stabil“.** Ohne eigene Wahl
  richtete sich der Kanal bisher danach, aus welchem Bau die laufende Fassung
  stammte – wer einmal eine Testfassung ausprobiert hatte, bekam von da an
  dauerhaft Testfassungen angeboten. Ein Kanalwechsel ist eine Entscheidung
  und soll auch eine bleiben; die Vorgabe ist deshalb „Stabil“. Eingestellte
  Kanäle bleiben unangetastet.

### Verbessert

- **„Beschwerdevorgang" gilt nicht mehr als Ortsname.** In der Überschrift
  „Aktennotiz – Beschwerdevorgang 12 C 345/26" schwärzte das Programm den
  Vorgang mit: Das Sprachmodell hielt ihn für einen Ort, und zwar unabhängig
  vom Umfeld. Aufgenommen ist nicht das einzelne Wort, sondern das
  **Grundwort** der Zusammensetzung – „vorgang" und „notiz" decken damit auch
  Geschäfts-, Buchungs- und Zahlungsvorgang oder die Telefonnotiz ab. Von
  dreißig geprüften Verwaltungsbegriffen lösten vorher drei einen Fehlalarm
  aus, jetzt keiner mehr; gefunden wird weiterhin alles, was danebensteht
  („Beschwerdevorgang: Bernd Meisinger" verliert den Namen, nicht die
  Überschrift).

- **Anonymisieren führt wieder Buch – für den Nachpass und das Protokoll.**
  In der anonymisierenden Betriebsart merkte sich das Programm die gefundenen
  Werte nicht. Zwei Dinge blieben dadurch stumm: der dokumentweite
  Konsistenz-Nachpass (ein Nachname, der später allein auftaucht, blieb
  stehen) und die Liste der Ersetzungen im Prüfprotokoll. Solange
  Anonymisieren die seltenere Wahl war, fiel das kaum auf – als Vorgabe wäre
  es der Regelfall geworden. Im Dokument ändert sich nichts: Der Platzhalter
  bleibt ohne Nummer.

- **„Kein personenbezogenes Datum" heißt jetzt „keine personenbezogene
  Angabe".** Im Rücknahme-Dialog und in der Gesichter-Warnung stand das
  juristische *Datum* – die Einzahl von „Daten". Gelesen wurde es als
  Kalendertag, zumal die Anwendung an anderer Stelle „Datumsangaben ebenfalls
  entfernen" anbietet. Es heißt jetzt überall „Angabe", so wie in den vier
  Gründen darüber im selben Fenster.

- **Die Herkunftszeile steht nur noch im „Über"-Fenster.** „Made with ♥ in
  Austria" saß unten im Hauptfenster mitten in der Knopfreihe und las sich
  dort wie eine weitere Schaltfläche. Sie steht weiterhin im
  „Über"-Fenster – dort, wo man sie sucht.

- **Die Ablagefläche hat jetzt eine sichtbare Kante.** Ihr gestrichelter
  Rand war so blass, dass er sich kaum vom Fenster abhob – das war
  gleichgültig, solange die Fläche nur eine Fläche war. Seit sie eine
  Schaltfläche ist, die man mit der Tabulatortaste anspringen kann, ist
  dieser Strich das Einzige, was sie als Bedienelement zeigt; er ist
  deshalb auf den Wert angehoben, den die Norm dafür verlangt.

## 0.10.22-beta.1 – 15. August 2026

### Neu

- **Wird die Zwischenablage-Überwachung abgeschaltet, ist sie wirklich aus.**
  Der Wächter hält die letzten Inhalte im Arbeitsspeicher, damit sich das
  Original zurücklegen lässt – bisher auch dann noch, wenn Sie die
  Überwachung ausgeschaltet hatten. Jetzt wird der Verlauf beim Abschalten
  vergessen. Das kostet die Wiederherstellung nach dem Ausschalten, und
  genau so ist es gemeint: Ausgeschaltet heißt ausgeschaltet.
- **Das Fehlerprotokoll enthält keine Dateipfade mehr.** Es lag nur auf Ihrem
  Rechner und wurde nie von selbst versendet – aber es führte Pfade im
  Klartext, und ein Dateiname verrät oft mehr als der Inhalt. Aus
  „…/Scheidung_Mueller_Vergleich.docx“ wird jetzt beim Schreiben
  `<datei>.docx`; die Endung bleibt, weil sie bei der Fehlersuche zählt.
  Dasselbe gilt für den Vermerk nach einem Absturz.
- **Die Liste der Ersetzungen warnt jetzt in sich selbst.** Sie ist die
  einzige Datei, in der Ihre Originaldaten im Klartext stehen, und sie liegt
  neben dem Ergebnis – wer einen Ordner weitergibt, gibt sie mit. Jetzt steht
  die Warnung als erste Zeile **in** der Datei, der Ausgabebereich nennt den
  vollständigen Pfad statt nur des Dateinamens, und auf der Kommandozeile
  wird die Datei überhaupt erst erwähnt: Dort erfuhr man bisher gar nicht,
  dass sie entstanden ist.
- **Anonymisieren oder pseudonymisieren ist jetzt eine benannte Wahl.** An
  der Stelle stand bisher ein Haken „Gleiche Namen gleich benennen – die KI
  erkennt dann noch, wer wer ist". Der beschrieb den Nutzen und verschwieg
  die Folge: Durchnummerierte Platzhalter (`[NAME_1]`, `[NAME_2]`) sind
  **Pseudonymisierung**, und pseudonymisierte Daten bleiben personenbezogene
  Daten – wer glaubte, damit anonymisiert zu haben, irrte. Jetzt stehen beide
  Verfahren nebeneinander, jedes mit seinem Preis. Die Vorgabe bleibt
  Pseudonymisieren, weil ein Dokument, das danach noch gelesen oder von einer
  KI verarbeitet wird, seine Bezüge braucht. Beim Anonymisieren ist die Liste
  der Ersetzungen gesperrt: Sie würde das Ergebnis wieder rückführbar machen.
  Handbuch und FAQ erklären den Unterschied in allen 18 Sprachen; auf der
  Kommandozeile heißt der Schalter jetzt auch `--anonymisieren`.
- **Die Zeile über der Ablagefläche sagt jetzt, was wirklich stimmt.** Sie
  versprach „100 % lokale Verarbeitung – ohne Cloud und Konto,
  DSGVO-freundlich". Für Ihre Dokumente trifft das zu, für das Programm nicht
  in dieser Pauschalität: Es sucht nach Aktualisierungen, meldet auf Wunsch
  Fehler, lädt Modelle nach und meldet gekaufte Arbeitsplätze an. Jetzt steht
  dort die engere und tragfähige Aussage: Ihre Dokumente verlassen den
  Rechner nicht.
- **Am Ergebnis steht jetzt immer, dass es zu prüfen ist.** Bisher meldete
  Maskuro nach einem glatten Lauf „12 Angabe(n) entfernt" in Grün und sonst
  nichts – das liest sich als Zusicherung, alles gefunden zu haben. Hinweise
  erschienen nur, wenn konkret etwas nicht geprüft werden konnte (Bilder,
  unbekannte Anhänge). Jetzt steht unter jedem Ergebnis unübersehbar, dass
  nicht in jedem Fall alle personenbezogenen Daten erkannt werden, dass die
  Prüfung beim Anwender liegt und dass Fehlendes von Hand zu ergänzen ist –
  im Fenster, im Ausgabebereich und auf der Kommandozeile. Kein Meldefenster
  zum Wegklicken: Der Satz steht dauerhaft da. Die Kurzanleitung sagt es
  jetzt im selben Wortlaut.
- **Nach einer Aktualisierung steht beim Start, was sich geändert hat.**
  Bisher lief eine Aktualisierung stumm durch und war von einem Neustart
  nicht zu unterscheiden. Jetzt erscheint einmalig „Was ist neu" – und wer
  eine Fassung übersprungen hat, sieht die dazwischen mit. Nicht beim
  allerersten Start: Dort führt weiterhin die Kurzanleitung ein.
- **Chinesisch und Japanisch finden jetzt Namen.** Bisher fanden sie
  **keine** – nicht wenige, keine. Beiden Sprachmodellen fehlte die
  Wortsegmentierung, ohne die ein Satz ohne Leerzeichen als ein einziges
  Wort gilt; das Programm wich still auf das mehrsprachige Ersatzmodell aus.
  Beide Sprachen erkennen nun Personen und Orte wie die übrigen. Das
  japanische Wörterbuch wird dabei zusammen mit der Sprache geladen und
  liegt nicht im Programm – es allein wäre gut 200 MB, die sonst jeder
  mitgetragen hätte.
- **Rumänien ist als Land wählbar.** Es fehlte bisher ganz. Damit werden
  rumänische Anschriften („Strada Victoriei 30"), Postleitzahlen mit Ort
  („010061 București") und der Cod Numeric Personal erkannt – Letzterer nur
  mit stimmender Prüfziffer, damit nicht jede dreizehnstellige Zahl auf einer
  Rechnung angestrichen wird. Bis dahin blieb in rumänischen Dokumenten die
  Postleitzahl neben dem geschwärzten Ortsnamen lesbar stehen.
- **„Seite rastern" im Editor.** Lässt sich Text aus einem PDF nicht
  entfernen – das kommt bei Dateien fremder Erzeuger vor –, wird die Seite
  jetzt auf Wunsch durch ihr Abbild ersetzt: Der Text ist damit
  unwiderruflich fort, die Seite bleibt lesbar und durchsuchbar. Die
  Warnung, die den Fall meldet, bietet den Schritt gleich als Knopf an;
  über „Werkzeuge → Seite rastern" geht er auch von sich aus. Rückgängig
  holt die Seite zurück.
- **Die Oberfläche gibt es jetzt auch auf Kroatisch, Griechisch, Litauisch,
  Slowenisch, Japanisch und Koreanisch.** Damit sind es achtzehn Sprachen. Handbuch,
  FAQ und Rechtstexte sind in allen sechsen vollständig dabei. Die
  Beschriftungen im bereinigten Dokument folgen dabei der Oberfläche – aus
  `[NAME_1]` wird `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]` oder `[氏名_1]`.
  **Bei Griechisch, Japanisch und Koreanisch stehen die Beschriftungen
  lateinisch** – `[ONOMA_1]`, `[SHIMEI_1]`, `[IREUM_1]`. Die Oberfläche
  bleibt in ihrer eigenen Schrift; nur was ins Dokument geschrieben wird,
  ist lateinisch. Grund ist der PDF-Zeichensatz: Dort waren griechische und
  japanische Beschriftungen zuvor als `[??_1]` angekommen, und damit ließ
  sich Name nicht mehr von Ort unterscheiden.
- **Neun Länder kommen dazu, und sieben bestehende werden vollständig.**
  Neu erkannt werden Ausweis-, Steuer- und Sozialversicherungsnummern samt
  Anschriften für **Kroatien, Slowenien, Griechenland, Litauen,
  Nordmazedonien, Russland, die Ukraine, China und Japan**. Bei den
  bestehenden Ländern sind Lücken geschlossen, die schwerer wogen: Für die
  **Niederlande** und **Portugal** gab es bisher gar keine Personennummer –
  die niederländische BSN und die portugiesische NIF wurden nicht erkannt,
  obwohl sie auf praktisch jedem Schriftstück dieser Länder stehen. Polen
  bekommt die Steuernummer NIP, Dänemark, Norwegen und Finnland ihre
  Anschriften, Kanada seine Postleitzahl. Damit sind es **35 Länder**.

### Entfernt

- **Für Linux gibt es vorerst kein Paket mehr.** Der Quelltext läuft dort,
  aber drei Dinge, die diese Anleitung verspricht, fehlen unter Linux:
  automatischer Start, globale Tastenkürzel und – je nach Arbeitsumgebung –
  das Symbol in der Leiste. Ein Paket auszuliefern, das weniger kann als
  beschrieben, wäre der falsche Weg. Windows und macOS sind unberührt.

### Verbessert

- **Aktenzeichen werden jetzt in allen Sprachen gefunden.** „Aktenzeichen
  12/2026-AB" wurde entfernt, „File reference 12/2026-AB" oder „Sygnatura
  12/2026-AB" blieben stehen: Die Feldwörter, an denen Maskuro so eine
  Nummer erkennt, gab es nur auf Deutsch. Jetzt kennt es die Entsprechungen
  in zwölf Sprachen – und wie bisher wird nur die Nummer ersetzt, die
  Beschriftung davor bleibt stehen, damit im Ergebnis erkennbar ist, was
  dort entfernt wurde.
- **Maskuro belegt im Leerlauf rund ein halbes Gigabyte weniger.** Beim Start
  wurde bisher auch das Zusatzmodell der genaueren Erkennung geladen, damit
  die erste Bereinigung nicht darauf wartet. Nachgemessen kostete das 648 MB
  Arbeitsspeicher und sparte 1,9 Sekunden – und es kostete sie auch dann,
  wenn Sie das Fenster nur öffnen und wieder schließen. Das Modell wird
  jetzt beim ersten Mal geladen, wenn es gebraucht wird; die Statuszeile
  sagt es an. Das Sprachmodell wird weiterhin beim Start geladen – das
  braucht die Zwischenablage-Überwachung sofort.
- **Die Ablagefläche ist jetzt auch ohne Maus zu bedienen.** „Dateien hierher
  ziehen" war eine Fläche, die auf Klicks reagierte – mit der Tastatur kam
  man nicht hin, und ein Bildschirmleser las sie als Rahmen mit Text darin
  vor, nicht als das, was sie ist. Sie ist jetzt eine Schaltfläche: Die
  Tabulatortaste springt sie an, Leer- und Eingabetaste öffnen die Dateiwahl,
  und wer angesprungen ist, sieht es an der Kante. Über das Menü „Datei →
  Dateien auswählen" ging es schon vorher, aber das musste man wissen.
- **Der Name der bereinigten Datei wird jetzt auch vorgelesen.** In der
  Dateiliste steht er als zweite, kleinere Zeile unter dem Original – aber
  er war dort nur gezeichnet, und ein Bildschirmleser nannte allein das
  Original. Ausgerechnet diese Zeile ist gegen den Irrtum gebaut, ein Lauf
  sei wirkungslos gewesen, weil im Ordner das unangetastete Original liegt.
  Die Zeile lautet jetzt vorgelesen „rechnung.pdf, Ergebnis:
  rechnung_bereinigt.pdf".
- **Bedienelemente ohne Beschriftung sagen jetzt, wofür sie da sind.** Die
  Symbolknöpfe in der Dateiliste, die Zeichenknöpfe im Nachbessern-Fenster
  und alle Auswahl- und Eingabefelder waren für Bildschirmleser namenlos –
  sie wurden als „Schaltfläche" und „Kombinationsfeld" angesagt, ohne wovon.
  Die Knöpfe an einer Zeile nennen dabei die Datei mit: In einer Liste mit
  zwanzig Einträgen hörte man sonst zwanzigmal denselben Satz.
- **Wer mit der Tastatur bedient, sieht wieder, wo er steht.** Der
  „Bereinigen"-Knopf und die Symbolknöpfe in der Dateiliste sind farbig
  angelegt, und damit hörte der Rahmen auf, den das System sonst um das
  angesprungene Bedienelement legt – beim Durchtabben sprang der Blick ins
  Leere. Beide haben jetzt einen eigenen Rahmen, sobald sie an der Reihe
  sind. Die Knöpfe ändern dabei ihre Größe nicht.
- **Sieben Schriftfarben waren zu blass, in beiden Erscheinungsbildern.**
  Nachgemessen nach der üblichen Norm (WCAG 2.1) lagen die blassen
  Hinweiszeilen, die Nebentexte auf der Ablagezone, die Punkte der Anleitung
  und im dunklen Bild zusätzlich das Blau und das Rot unter der Grenze von
  4,5:1 – lesbar bei gutem Licht und gutem Auge, sonst nicht. Alle sind
  angehoben; die Abstufung bleibt, die Texte lesen sich weiterhin als
  Nebentexte. Drei weitere – die Farben, in denen Warnungen und Erfolg
  gemeldet werden – hielten die Grenze nur knapp und sind mitgezogen: Wer
  sie nicht liest, liest die Auskunft nicht, ob etwas schiefging. Sichtbar
  verändert hat sich dabei nur der „Bereinigen"-Knopf im dunklen Bild: Er
  trägt jetzt dunkle statt weißer Schrift, wie die Akzentknöpfe von
  Windows 11 auch.
- **Jede Zeile der Dateiliste hat jetzt ihr eigenes Kreuz.** Bisher musste
  man die Zeile erst auswählen und dann auf „Entfernen" klicken – zwei
  Schritte für eine Kleinigkeit. Das Kreuz steht rechts in der Zeile und
  braucht einen. Der Knopf „Entfernen" darunter ist damit entfallen; wer
  mehrere Zeilen auf einmal loswerden will, wählt sie aus und nimmt den
  Eintrag im Kontextmenü, der auch sagt, wie viele es sind. „Alle entfernen"
  bleibt. Aus der Liste genommen wird immer nur die Zeile – nie eine Datei
  auf der Platte.
- **Vor der KI-Prüfung steht jetzt, ob dieser Rechner dafür taugt.** Bisher
  stand im Fenster nur, wie groß das Modell ist. Wer es auf einem schwachen
  Rechner einschaltete, merkte erst beim ersten Dokument, dass es sehr lange
  dauert – nach 5,4 GB Download. Jetzt nennt das Fenster **vorher**
  Arbeitsspeicher und freien Platz und sagt, was das bedeutet; **nachher**
  wird die Geschwindigkeit gemessen und in der Größe genannt, um die es geht:
  „Ein zehnseitiges Dokument dauert auf diesem Rechner etwa 12 Minuten." Ist
  es zu langsam, rät das Programm ab und bietet an, die Stufe wieder
  auszuschalten – verbieten tut es nichts.
- **Die Geschwindigkeitsmessung läuft jetzt auf jedem Rechner.** Bisher kam
  sie nur, wenn zusätzlich die Grafikbeschleunigung eingerichtet wurde – die
  es nur unter Windows gibt. Auf allen anderen Rechnern schätzte das Programm
  die Dauer deshalb anhand eines fremden Rechners, und ausgerechnet dort, wo
  es langsam ist, lag die Schätzung daneben.
- **Türkische Anschriften werden auch im Scan gefunden.** Auf einem
  eingescannten Briefkopf blieb „34710 İstanbul" lesbar stehen, während
  dieselbe Angabe im Text daneben verschwand: Die Texterkennung liest das
  türkische İ ohne seinen Punkt, und das Muster erwartete einen
  Großbuchstaben. Gleiches galt für „Bağdat Caddesi".
- **Spanische Anschriften ohne eigenen Straßennamen werden gefunden.**
  „Gran Vía 5" blieb stehen, weil das Muster hinter dem Straßentyp noch ein
  Namenswort erwartete – bei „Calle Mayor" gibt es eines, bei „Gran Vía"
  ist der Typ selbst schon der Name. Gleiches gilt jetzt für „La Rambla"
  und „Castellana".
- **Im Fenster „Über dieses Programm" steht jetzt ein Transparenzhinweis**
  dazu, dass die Anwendung mit Unterstützung Künstlicher Intelligenz
  entwickelt wurde. Er betrifft die Entstehung des Programms, nicht seine
  Arbeitsweise: Bereinigt wird weiterhin ausschließlich auf dem eigenen
  Rechner.
- **„Sprachen verwalten" zeigt jetzt die brauchbaren Sprachen zuerst.** Für
  die Hälfte der 48 Sprachen gibt es kein eigenes Sprachmodell; dort erkennt
  ein mehrsprachiges Ersatzmodell Namen nur schwach, in manchen Schriften
  gar nicht. Nebeneinander in einer Liste sahen alle gleichwertig aus. Die
  Vorgabe zeigt daher nur noch Sprachen mit eigenem Modell – über
  „Angezeigt" lassen sich die übrigen jederzeit einblenden, mit einem Satz
  dazu, was sie können und was nicht. Es fällt nichts weg, und wer eine
  eingeschränkte Sprache eingerichtet hat, behält sie.
- **Die Frage nach einer fehlenden Sprache nennt jetzt den Ausweg.** Wird
  eine Sprache erkannt, für die noch nichts eingerichtet ist, bot das
  Programm bisher nur „Laden" oder „Ohne fortfahren" an. Die Erkennung kann
  aber danebenliegen – bei kurzen Formularen und Listen mit wenig Fließtext
  entscheiden wenige Wörter. Im Fenster steht deshalb jetzt, dass man
  abbrechen und die richtige Sprache von Hand auswählen kann, statt
  „Automatisch erkennen" zu verwenden. Das erspart im Zweifel einen
  Download von mehreren hundert Megabyte für eine Sprache, die gar nicht
  gebraucht wird.
- **Platzhalter-Beschriftungen sprechen jetzt die Oberflächensprache.**
  „[NAME_1]", „[ADRESSE_2]" & Co. standen bisher immer auf Deutsch, ganz
  gleich welche Sprache eingestellt war oder in welcher Sprache das
  Dokument verfasst ist. Jetzt folgen sie der Oberflächensprache – bei
  Englisch also „[NAME_1]", „[ADDRESS_2]". Nicht der Dokumentsprache: Die
  ist bei „automatisch erkennen" geraten und manchmal falsch; die
  Oberflächensprache ist es nie.
- **Weniger Nachfragen beim Nachbessern.** Wohin das Ergebnis gespeichert
  wird, steht jetzt dauerhaft unten in der Leiste („→ vertrag_bereinigt.pdf",
  im Tooltip der Ordner) – ein Klick darauf wählt einen anderen Ort, ohne
  gleich zu speichern. Die Rückfrage beim ersten Speichern entfällt damit.
  Die Frage „schon bearbeitet – neu beginnen?" lässt sich für die Sitzung
  merken, und zwei Hinweisfenster, die nur eine Auskunft gaben, stehen jetzt
  in der Statuszeile. Geblieben sind die Fragen, die einen nicht
  zurücknehmbaren Schaden verhindern: die ungespeicherte Arbeit beim
  Schließen und die Warnung über nicht entfernten Text.
- **Das Ergebnis sagt jetzt, wo der Scan selbst nicht lesbar war.** Auf einem
  eingescannten Dokument liest die Texterkennung des Geräts nicht alles
  richtig – aus „Solarstraße 9" wird dann etwa „Solaret^aß« B". Was so
  verlesen wurde, kann keine Prüfung mehr finden: Es sieht für jedes
  Suchmuster wie Buchstabensalat aus. Das Programm kann daran nichts ändern,
  benennt solche Stellen jetzt aber mit Seitenzahl – meist stecken dort
  Stempel, Briefköpfe oder handschriftliche Zusätze. Ein Hinweis, keine
  Warnung: Bei einem gesetzten Dokument bleibt er aus.
- **Die Dateiliste zeigt jetzt, wie das Ergebnis heißt.** Unter dem
  Dateinamen steht nach dem Lauf der Name der bereinigten Datei
  („→ vertrag_bereinigt.pdf"). Bisher stand er nur im Protokoll hinter
  „Details", und wer im Ordner nachsah, fand das unangetastete Original.
  Der Name der Quelle bleibt stehen – sonst wäre nicht mehr zu sehen, aus
  welcher Datei ein Ergebnis stammt.
- **Die Knöpfe in einer fertigen Zeile sind größer und deutlicher.**
  Ansehen, Nachbessern und „Im Ordner zeigen" waren flache Symbole ohne
  Fläche und gingen in der Liste unter – dabei sind sie nach dem Lauf das
  Einzige, was man noch anklickt.

### Behoben

- **Auf fremdsprachiger Oberfläche wurden eigene Regeln zum Schwärzen,
  Maskieren und Hashen stillschweigend übergangen.** Wer festgelegt hatte,
  dass Namen geschwärzt statt ersetzt werden, bekam sie trotzdem ersetzt –
  sobald das Programm nicht auf Deutsch oder Englisch bedient wurde. Die
  Einstellung stand da, sie wirkte nur nicht, und im Ergebnis war der
  Unterschied nicht zu sehen. Betroffen waren neun der zwölf
  Oberflächensprachen.
- **Die Einstellung „Sprache der Beschriftungen“ hatte außerhalb von
  Deutsch und Englisch keine Wirkung.** „Deutsch“ und „Englisch“ ließen
  sich wählen, im Dokument stand aber weiter die Sprache der Oberfläche.
  Jetzt wirken alle drei Möglichkeiten; die Voreinstellung „wie die
  Oberfläche“ liefert unverändert dasselbe wie bisher.
- **In kurzen Textausschnitten blieben Namen stehen – etwa in einem
  kopierten Mailzitat.** Wer einen Ausschnitt über die Zwischenablage
  bereinigte, bekam dort oft nur die E-Mail-Adresse geschwärzt, den Namen
  darunter aber nicht. Ausschlaggebend war die schiere Zeilenzahl: Ab
  sechs Zeilen erkannte das Programm den Ausschnitt als Aufstellung und
  fand die Namen, darunter nicht – ein kopiertes Mailzitat hat fünf. Eine
  beliebige zusätzliche Zeile, etwa ein Betreff, kippte das Ergebnis. Jetzt
  genügen vier Zeilen, und in der Messung verschwinden alle geprüften Namen
  statt eines Drittels. Auf längere Dokumente und auf Fließtext wirkt sich
  das nicht aus.
- **Die Grafikbeschleunigung der KI-Prüfung wurde bisher wieder
  abgeschaltet, sobald man sie eingerichtet hatte.** Nach dem Einrichten
  misst das Programm, ob die Grafik auf diesem Rechner wirklich schneller
  ist als der Prozessor – diese Messung schlug jedoch immer fehl, ohne es
  zu sagen, und das Ergebnis „beide gleich schnell" entschied für den
  Prozessor. Wer die 65 MB geladen hatte, bekam danach weniger als vorher.
  Die Messung läuft jetzt; scheitert sie, ändert sie nichts mehr.
- **Die Zeitschätzung rechnete auf jedem Rechner mit fremder
  Geschwindigkeit.** Sie stützt sich auf dieselbe Messung; solange die
  nicht lief, galt der Wert des Entwicklungsrechners. „Etwa zwei Minuten"
  konnte damit auf einem langsamen Rechner eine halbe Stunde bedeuten.
- **Die KI-Stufe arbeitet mit einem neuen, deutlich besseren Sprachmodell**
  (Qwen3.5-9B statt Qwen3-4B) und ist nicht mehr auf Deutsch und Englisch
  beschränkt, sondern arbeitet in zwölf Sprachen. Gemessen über den
  Prüfkorpus: gleich viele gefundene Angaben wie ohne die Stufe, aber
  weniger als halb so viele überflüssige Schwärzungen (75 → 31). Das Modell
  ist größer (5,4 statt 2,4 GB) und braucht etwa die doppelte Rechenzeit;
  beim Einschalten wird es einmalig geladen, das alte dabei entfernt.
- **Anschriften in Französisch, Italienisch, Spanisch, Portugiesisch,
  Polnisch, Türkisch und Schwedisch werden jetzt vollständig entfernt.**
  Bisher verschwand dort nur
  der Straßen- und Ortsname – Hausnummer und Postleitzahl blieben lesbar
  stehen („[ORT_1] 28, 28013 [ORT_2]“). Für diese Sprachen gab es keine
  eigenen Adressmuster; sie sind jetzt ergänzt.
- **Griechisch und Koreanisch fanden überhaupt keine Namen.** Bei Griechisch
  lag es am Ersatzmodell – mit dem eigenen Modell, das sich jetzt laden
  lässt, werden Namen und Orte sauber erkannt. Bei Koreanisch lag es am
  Programm: Es setzte voraus, dass ein Name mit einem Großbuchstaben
  beginnt, und Hangul kennt keine Großbuchstaben. Betroffen waren vor allem
  kurze Einheiten – Tabellenzellen, Formularfelder, Listeneinträge.
- **Ein Sprachmodell, das sich nicht laden ließ, brach die Bereinigung ab.**
  Statt einer Fehlermeldung springt jetzt das mehrsprachige Modell ein, und
  das Ergebnis weist darauf hin, dass mit der schwächeren Erkennung
  gearbeitet wurde. Betrifft derzeit Chinesisch und Japanisch, deren
  Modelle eine Worttrennung benötigen, die dem Programm noch nicht beiliegt.
- **Eine Sprache mit eigenem Modell galt als installiert, sobald irgendeine
  andere geladen war.** Wer etwa Türkisch einrichtete, bekam damit das
  mehrsprachige Ersatzmodell – und Chinesisch, Japanisch, Koreanisch oder
  Griechisch standen daraufhin mit gesetztem Haken und „0 MB" in der Liste,
  obwohl ihr eigenes Modell fehlte. Sie ließen sich dadurch nie nachladen
  und arbeiteten dauerhaft mit dem schwächeren Ersatz. Jetzt zeigt die
  Liste den tatsächlichen Stand samt Ladegröße.
- **Eine ausgefallene Erkennungsstufe schwieg.** War „Erweiterte Erkennung"
  oder „Maximale Erkennung (KI)" eingeschaltet, ließ sich das Modell aber
  nicht ausführen, arbeitete das Programm ohne die Stufe weiter – ohne ein
  Wort darüber. Das Ergebnis sah aus wie jedes andere, und der Schalter
  stand weiter auf „an": Man hielt also das Ergebnis der Grundstufe für das
  Beste, was zu holen war. Das Ergebnis sagt es jetzt und nennt beides – was
  nicht geprüft wurde und wie sich das Modell erneut laden lässt. Der Fall
  ist nicht selten: Auf manchen Rechnern scheitert die KI-Stufe beim Laden,
  wenn die Grafikbeschleunigung fehlt.
- **Ein Fehler beim Laden des Zusatzmodells brach die ganze Bereinigung
  ab.** Bei „Erweiterte Erkennung" war nur die Auswertung des Modells
  abgesichert, nicht sein Einlesen – und genau dort geht es schief, wenn die
  Datei beschädigt ist oder nicht zum Rechner passt. Statt einer Fehlermeldung
  gibt es jetzt ein Ergebnis der Grundstufe samt Hinweis.
- **Eine Sprache ließ sich nicht mehr entfernen – und damit auch nicht neu
  laden.** Wer in „Sprachen verwalten" den Haken wegnahm und die Änderung
  übernahm, las „Deutsch entfernt", sah den Haken aber sofort wieder gesetzt.
  Ursache war die Übernahme aus dem Programmordner: Bei einer Installation
  für alle Benutzer liegen die Sprachmodelle schreibgeschützt im
  Programmordner, und das Programm holt sich fehlende von dort, statt
  hunderte Megabyte neu zu laden. Diese Übernahme lief bei jedem Zugriff
  mit – und kopierte die eben gelöschte Sprache im selben Atemzug zurück.
  Sie geschieht jetzt einmalig; nachgeladene Sprachmodelle bleiben dabei
  erhalten. Außerdem sieht das Programm nach dem Löschen nach: Was sich
  nicht entfernen ließ, wird jetzt als Fehlschlag gemeldet statt als
  „entfernt".
- **Bei einer Installation für alle Benutzer ließ sich Nachgeladenes nicht
  ablegen.** Wer das Programm für alle Benutzer installiert, hat es in
  „Programme", und dorthin darf ohne Verwalterrechte nichts geschrieben
  werden. Für die Sprachmodelle war dafür längst ein Ausweichort vorgesehen,
  für anderes nicht:
  - Die **Seitenansicht-Komponente** wurde nach 290 MB Download in den
    Programmordner entpackt und scheiterte dort – ohne einen Grund zu
    nennen. Sie liegt jetzt bei den Sprachmodellen, wo sie laut Absicht
    immer liegen sollte.
  - Die **Grafikbeschleunigung** kann nicht ausweichen: Sie tauscht
    Bibliotheken im Programm selbst aus. Statt erst zu laden und dann
    wortlos zu scheitern, sagt das Programm nun vorher, dass es hier nicht
    geht und was das bedeutet – die maximale Erkennung arbeitet weiter, nur
    über den Prozessor.
  - Eine mitgelieferte **Sprache der Texterkennung** ließ sich nicht
    entfernen: Sie wurde aus dem Programmordner sofort wieder hergestellt.
    Dieselbe Ursache wie bei den Sprachmodellen, dieselbe Behebung.
  - Beim Entfernen einer Sprache konnten **Sprachdaten einer fremden
    Tesseract-Installation** gelöscht werden. Angetastet wird jetzt nur noch
    der eigene Ordner.
  - Der Ausweichort galt bisher nur unter Windows. Ein Linux-Archiv nach
    `/opt` hatte dieselbe Not ohne denselben Ausweg.
- **Beim Nachbessern verschwand eine ganze Zeile, obwohl nur ein Wort
  gerahmt war.** Wer in einer bereits bereinigten Datei einen Platzhalter
  schwärzte, verlor die Zeile, in der er stand: Aus „Sehr geehrte Frau
  Doktor [NAME_1]" blieb nichts übrig – und die Meldung sagte dazu „ein Wort
  aus dem Dokument entfernt". Betroffen war jede Datei, die schon einmal
  durch das Programm gelaufen war, also gerade der Fall, für den es das
  Nachbessern gibt. Der übrige Text bleibt jetzt stehen, an unveränderter
  Stelle.
- **„EMPLOYEES" über einer Namensliste wurde selbst geschwärzt.** Derselbe
  Fall wie „MITARBEITER" in 0.10.19, nur auf Englisch – dort war er
  geblieben. In Versalien fehlt dem Sprachmodell das
  Unterscheidungsmerkmal, und die Überschrift steht über lauter echten
  Namen. Die Namen darunter werden weiterhin gefunden. Nicht aufgenommen
  wurde „staff": Das ist ein belegter Nachname, und der Eintrag nähme jeden
  „John Staff" mit – dieselbe Abwägung wie seinerzeit bei „Arbeiter".
- **Die Rechtsform wurde ein zweites Mal ersetzt.** Auf einem
  eingescannten Briefkopf las das Sprachmodell „GmbH", die Anschrift und
  die Postleitzahl als **einen** Ort. Anschrift und Postleitzahl
  schnitten sich danach ihre Stücke heraus, und übrig blieb die
  Rechtsform als eigener Treffer: Im Ergebnis stand „[ORT_1] [ORT_2]", wo
  „[ORT_1] GmbH" gemeint war. Der Firmenname wird weiterhin ersetzt – nur
  der nackte Zusatz bleibt jetzt stehen, und das Ergebnis liest sich wie
  ein Briefkopf statt wie eine Lückentext-Übung.
- **Ein zurechtgeschnittener Treffer wurde nicht erneut geprüft.** Die
  Ursache des Falls darüber, und sie reicht weiter: Die Filter gegen
  geratene Treffer liefen auf dem, was die Erkenner **melden** – nicht auf
  dem, was nach der Überlappungsauflösung übrig bleibt. Wird ein langer
  Treffer an einem stärkeren Erkenner beschnitten, ist das Bruchstück ein
  anderer Text als der beurteilte, und niemand sah es sich noch einmal an.
  Jetzt schon.
- **„Sie verwenden die neueste Fassung" – obwohl gar nicht nachgesehen
  werden konnte.** Wer als Aktualisierungskanal „Vorschau (Beta)" oder
  „Stabil – empfohlen" eingestellt hatte, bekam diese Auskunft, dabei ist
  auf diesen Kanälen bisher überhaupt nichts erschienen. Jetzt sagt das
  Programm genau das – und schlägt vor, in den Einstellungen einen anderen
  Kanal zu wählen.
- **Das Fenster während des Ladens schließen ließ einen Faden abstürzen.**
  Wer Maskuro startete und das Fenster gleich wieder zumachte, während die
  Sprachmodelle noch geladen wurden, bekam im Protokoll einen Fehlerbericht:
  Der Ladevorgang meldete sich bei einem Fenster, das es nicht mehr gab.
  Sichtbare Folgen hatte das keine, aber im Protokoll stand ein Absturz, wo
  nur jemand schneller war als das Programm.
- **Das Ergebnis wird jetzt angesehen, nicht nur nachgelesen.** Bisher galt
  eine Seite als sauber, wenn der Wert nicht mehr im Text stand. Auf einem
  Scan ist das kein Beweis – dort ist der sichtbare Text ein Bild. Zum
  Schluss wird deshalb nachgesehen, ob die Fläche im Ergebnis wirklich
  geschwärzt ist; steht dort noch helles Papier, sagt es der Bericht
  ausdrücklich, statt „ersetzt" zu melden.
- **Eine ersetzte Angabe blieb im Bild stehen.** Stand der Wert auf einem
  Bild – ein eingescannter Briefkopf, ein Stempel, eine ganze gescannte
  Seite –, wurde er zwar aus dem Dokumenttext entfernt, war aber weiterhin
  zu **sehen**: Was der Mensch liest, sind dort Bildpunkte. Der Bericht
  meldete trotzdem „ersetzt". Jetzt wird die Fläche im Bild geschwärzt,
  gleich welche Strategie eingestellt ist, und der Platzhalter steht hell
  auf diesem Grund – hässlich, aber ehrlich, und die Zuordnung bleibt
  erhalten. Lässt sich ein Bildformat nicht bearbeiten, sagt das Ergebnis
  es jetzt ausdrücklich, statt sauber auszusehen.
- **Auf einem Scan fehlte der Platzhalter ganz.** Die Textschicht einer
  gescannten Seite wird unsichtbar gezeichnet, und ein Platzhalter, der in
  sie eingefügt wurde, erbte das: gesetzt, aber nicht zu sehen. An der
  Fundstelle stand danach nichts.
- **Eine Texterkennung, die gar nicht laufen konnte, galt als bestanden.**
  Fehlte die Sprachdatei oder brach die Erkennungs-Maschine ab, meldete der
  Bericht „Bild(er) … wurden per Texterkennung geprüft (0 Fundstelle(n))" –
  also eine Prüfung, die nie stattfand. Bei einem Scan ist das die einzige
  Prüfung überhaupt: Ein Vertrag mit lesbarer Anschrift im Seitenbild galt
  damit als fertig. Jetzt sagt der Bericht, dass nichts geprüft wurde, und
  warum.
- **Die Sprachdatei wurde im falschen Ordner gesucht.** Lagen im eigenen
  Sprachverzeichnis andere Sprachen als die des Dokuments, bekam die
  Erkennungs-Maschine genau dieses Verzeichnis vorgesetzt und scheiterte –
  obwohl die passende Sprache daneben lag. Gesucht wird jetzt die
  **Sprache**, nicht der Ordner.
- **Die Warnung über nicht entfernten Text riet zu etwas, das es nicht
  gibt.** Sie verwies auf „Als PDF schwärzen" – das erzeugt aber eine
  PDF-Ansicht von *Office*-Dateien und steht bei einem PDF gar nicht zur
  Verfügung. Wer der Warnung folgen wollte, suchte vergeblich. Jetzt steht
  dort der Knopf, der die Sache erledigt.
- **Im Editor landeten Balken und Platzhalter neben der markierten
  Stelle.** Betroffen war jedes PDF, in dem eine Zeile auf einem
  Trennstrich endet und das Wort in der nächsten weitergeht – bei Scans
  fällt das besonders auf, weil Vertragstexte durchgehend getrennt gesetzt
  sind. Die beiden Zeilenhälften galten als *ein* Wort, das quer über den
  Satzspiegel reicht, und jeder Rahmen in seiner Nähe übernahm diese
  Ausdehnung. Die Erkennung selbst ändert sich dadurch nicht: Der
  Messkorpus liefert dasselbe Ergebnis wie zuvor.
- **Der Editor warnte, der Text stehe „immer noch im Dokument", obwohl er
  entfernt war.** Kam dasselbe Wort mehrfach auf einer Seite vor – in
  Verträgen die Regel –, meldete die Selbstprüfung nach jedem Eingriff
  einen Fehlschlag. Sie zählt jetzt die Vorkommen, statt bloß
  nachzusehen, ob das Wort noch irgendwo steht. Bei einem echten
  Fehlschlag warnt sie unverändert.
- **Die Ergebnisdatei hieß in jeder Sprache „_bereinigt".** Gemeint war
  immer, dass der Namenszusatz der Oberflächensprache folgt – auf Englisch
  tat er das auch („_cleaned"), in den übrigen sechzehn Sprachen nicht. Wer
  das Programm auf Finnisch benutzte, bekam „asiakirja_bereinigt.pdf". Jetzt
  heißt die Datei „asiakirja_puhdistettu.pdf", auf Japanisch
  „書類_除去済み.pdf" und so fort – jeweils mit dem Wort, das dieselbe
  Oberfläche in ihrer Fertigmeldung benutzt. Wer einen eigenen Zusatz
  eingestellt hat, behält ihn.
- **„Sprachen verwalten" beschriftete sich immer deutsch.** In der Liste der
  48 Dokumentsprachen standen die deutschen Namen, gleich welche Oberfläche
  eingestellt war: Ein finnischer Anwender las „Chinesisch". Jetzt steht dort
  der Name in seiner Sprache und dahinter der Eigenname – „Kiina (中文)".
  Der Eigenname ist Absicht: Wer die Sprache am eigenen Namen erkennt,
  findet sie auch dann, wenn ihm das finnische Wort nichts sagt.

## 0.10.19 – 12. August 2026

### Verbessert

- **Der Eintrag im Kontextmenü spricht jetzt Ihre Sprache.** Bisher stand
  dort auf jedem System der deutsche Wortlaut – auch auf einem englischen
  Windows. Jetzt folgt er der eingestellten Oberflächensprache, und wer die
  Sprache umstellt, bekommt den Eintrag sofort umbenannt, ohne neu zu
  installieren. (Windows; unter macOS und Linux ist der Menüname zugleich
  ein Dateiname – das kommt später.)
- **Der Editor merkt sich, in welcher Ansicht Sie zuletzt gearbeitet
  haben.** Wer die Seitenansicht benutzt, bekommt sie beim nächsten
  Dokument von selbst – ohne sie jedes Mal einzuschalten. Wer sie nie
  benutzt hat, merkt nichts davon: Sie wird nur wiederhergestellt, wenn der
  dafür nötige Baustein bereits geladen ist, nie wird dafür etwas
  nachgeladen.

### Behoben

- **„MITARBEITER" über einer Namensliste wurde selbst geschwärzt.** In
  Mitarbeiterverzeichnissen und Organigrammen verschwand die Überschrift
  als vermeintlicher Name – sie steht dort über lauter echten Namen, und in
  Großbuchstaben fehlt dem Sprachmodell das Unterscheidungsmerkmal. Die
  Namen darunter werden weiterhin gefunden.
- **Mengenangaben wurden für Anschriften gehalten.** In Rechnungen,
  Lieferscheinen und Lagerlisten verschwanden Angaben wie „3390 Protokoll",
  „1030 Betrag" oder „3390 Lager" als vermeintliche Postleitzahl mit Ort –
  vierstellig sieht jede Menge aus wie eine österreichische Postleitzahl.
  Steht hinter der Zahl ein Wort, das die Anwendung als Sachwort,
  Abteilung, Tätigkeit oder Feldbeschriftung kennt, bleibt es jetzt stehen.
  Echte Ortsangaben sind unberührt, auch solche, die zugleich ein solches
  Wort sind („4692 Ort"). Nicht gelöst ist damit der Fall, dass hinter der
  Zahl ein ganz gewöhnliches Wort steht („3390 Regal") – dafür braucht es
  ein Postleitzahlenverzeichnis.
- **Die Hilfe nannte einen Menüpunkt, den es nicht gibt.** Anleitung, Bild
  und die Meldung am Ende der Installation sprachen von „Dokument für KI
  bereinigen"; der Eintrag im Kontextmenü heißt aber „Personenbezogene
  Daten entfernen". Wer der Hilfe folgte, suchte vergeblich. Alle drei
  Stellen nennen den Menüpunkt jetzt so, wie er wirklich heißt.
- **„Mit dem System starten" ließ sich nicht abschalten.** Wer beim
  Installieren „Mit Windows starten" angekreuzt hatte, sah in den
  Einstellungen trotzdem einen leeren Haken – und schwerer: Ein- und
  Ausschalten in der Anwendung blieb wirkungslos, das Programm startete
  weiter mit Windows. Grund waren zwei Orte, an denen Windows nach
  Startprogrammen sieht; die Anwendung kannte nur einen davon. Jetzt zählt
  beides, der Schalter zeigt den wahren Zustand und wirkt in beide
  Richtungen. Auch berücksichtigt: Wer den Eintrag im Task-Manager
  abschaltet, sieht das jetzt in der Anwendung – und wer dort wieder
  einschaltet, hebt die Abschaltung damit auf.
- **Überschriften über Namenslisten wurden geschwärzt.** „TEILNEHMERLISTE
  WERKSTATTGESPRÄCH" oder „MITARBEITERÜBERSICHT INNENDIENST" über einer
  Liste von Personen verschwanden als vermeintlicher Name. In
  Großbuchstaben fehlt dem Sprachmodell sein bestes Erkennungszeichen, und
  im Deutschen ist jedes Substantiv großgeschrieben – „Teilnehmerliste
  Werkstattgespräch" sieht dann aus wie „Anna Huber". Zusammensetzungen
  auf `-liste`, `-dienst`, `-gespräch`, `-sitzung` und `-besprechung`
  bleiben jetzt stehen. Die Grundwörter allein gelten weiterhin als Name:
  *Liste* und *Dienst* sind belegte Nachnamen, *Teilnehmerliste* ist keiner.
- **Hochkant gesetzte Angaben bekamen einen unlesbaren Platzhalter.**
  Aktenzeichen am Seitenrand, Bearbeiterkürzel neben dem Bundsteg,
  hochkante Tabellenköpfe: Solche Angaben wurden zwar gefunden und
  entfernt, der Platzhalter kam aber quer über dem Text heraus, auf ein
  bis zwei Punkt zusammengedrückt und mitunter über die Papierkante
  hinaus. Jetzt folgt er dem Text – senkrecht, in Lesegröße und in
  derselben Richtung, in der die Angabe stand. Dasselbe galt für Seiten,
  die nachträglich gedreht wurden (waagrecht geschriebener Text mit
  eingetragener Seitendrehung, wie ihn manche Ausgabeprogramme liefern);
  auch dort steht der Platzhalter jetzt so, wie man die Seite ansieht. „Sehr
  geehrte Frau Doktor Anneliese Berger" ergab nur „Anneliese" als Namen –
  „Berger" blieb im Dokument. Dasselbe traf jeden Namen mit Zweitnamen
  („Frau Anna Maria Berger"). Grund war die Regel für den Namen hinter
  einer Anrede: Sie hatte zwei Wortstellen, und ein Titel oder ein
  Zweitname verbrauchte die erste. Mit „Dr." fiel es nie auf – der Punkt
  bricht die Regel, und das Sprachmodell erwischte den ganzen Namen.
  Jetzt werden Titel übersprungen, ohne einen Platz zu kosten, und der
  Name darf aus drei Teilen bestehen. Eine Rolle **hinter** dem Namen geht
  weiterhin nicht mit: „Frau Anna Huber Geschäftsführerin" ersetzt den
  Namen, nicht die Rolle.

## 0.10.18 – 12. August 2026

### Behoben

- **Ersetzen im Editor ging auf gedrehten Seiten schief.** Der Platzhalter
  stand hochkant, ließ sich oft gar nicht setzen („kein Platz", wo
  reichlich war) und wurde dann still zu einem schwarzen Balken – die
  Zuordnung führte trotzdem eine Ersetzung, und das Zurückholen meldete
  später „Platzhalter nicht gefunden". Das Schwärzen war seit dem
  10. August umgerechnet, das Ersetzen nicht.
- **Auf Scans wird jetzt genau das geschwärzt, was auch entfernt wurde.**
  Bisher folgten die beiden verschiedenen Grenzen: Aus dem Dokument fiel,
  was die Schwärzung erwischte – manchmal mehr als der Rahmen, weil Text
  hinter einer Fundstelle mitfällt –, unkenntlich gemacht wurde im Bild
  aber nur der gezogene Rahmen. Auf einem Scan blieb damit lesbar stehen,
  was das Programm längst für entfernt hielt. Jetzt deckt die
  Bildschwärzung jedes entfernte Zeichen ab.
- **„Original zeigen" heißt jetzt „Vorher/Nachher" und steht abgesetzt.**
  Neben der Seitenansicht las es sich wie eine zweite Darstellungsart –
  dabei geht es um etwas ganz anderes: Die Seitenansicht bestimmt, **wie**
  gezeigt wird, der Vergleich, **was**. Jede Kombination ist möglich; ein
  Trennstrich in der Leiste sagt das jetzt, bevor jemand fragen muss.
- **Das erste Speichern im Editor zeigt, wohin es geht.** Bisher legte es
  die Datei stumm als `<name>_bereinigt.<ext>` neben das Original –
  regelkonform, aber im Editor unerwartet: Man drückt Speichern und sucht
  danach, wo die Datei hin ist. Jetzt steht der Ort einmal je Datei da,
  mit „Speichern" und „Anderer Ort …" daneben. Weitere Male schreiben
  wieder stumm an denselben Platz.
- **Das Schwärzen sagt jetzt, was es bewirkt hat.** Statt „Bereich
  geschwärzt." steht dort, wie viele Wörter aus dem Dokument entfernt
  wurden – und wenn unter dem Rahmen gar kein Text lag, ausdrücklich das.
  Auf einem Scan war das bisher nicht zu erkennen: Der sichtbare Text
  steht dort als Bildpunkte, und ob die Textschicht darunter gefallen
  ist, zeigt kein Bild.
- **Eine erneut hereingezogene Originaldatei zeigte stillschweigend die
  alte Fassung.** Wer eine schon bearbeitete Datei noch einmal öffnete,
  landete ohne Hinweis wieder auf dem bisherigen Ergebnis – mitsamt den
  alten Balken. Jetzt wird gefragt: vom Original neu beginnen oder am
  Ergebnis weiterarbeiten. Voreingestellt ist „neu beginnen"; das
  Ergebnis bleibt in beiden Fällen erhalten.
- **„Nicht genug Platz, um … zurückzuholen" kam auf gedrehten Seiten
  immer.** Die Vorabprüfung verwechselte „diese Seite übernimmt der
  Zeichenweg" mit „kein Platz" und verweigerte das Zurücknehmen einer
  Ersetzung grundsätzlich, sobald die Seite gedreht war.
- **Der Editor sieht jetzt selbst nach, ob das Entfernen gewirkt hat.**
  Nach jedem Schwärzen und Ersetzen wird die geschriebene Datei erneut
  gelesen und geprüft, ob der Text im Rahmen wirklich verschwunden ist.
  Steht er noch da, erscheint eine deutliche Warnung samt Rat, die Seite
  zu rastern – statt einer Erfolgsmeldung über eine Bereinigung, die nicht
  stattgefunden hat. Damit fallen auch PDF-Erzeuger auf, die wir nie
  gesehen haben.
- **Auf einem Scan lag der Platzhalter über dem alten Wort.** Dort steht
  der sichtbare Text als Bildpunkte, und die wurden nur unter schwarzen
  Balken geräumt, nicht unter Platzhaltern. Jetzt entsteht unter dem
  Platzhalter weißer Grund – lesbar, statt doppelt beschriftet.

## 0.10.17 – 11. August 2026

### Neu

- **Das Prüfprotokoll ist jetzt unterschrieben.** Mit einer Firmenlizenz
  trägt jede Protokollzeile eine Unterschrift – erzeugt mit einem
  Schlüssel, der in der Lizenz steckt und den Rechner nie verlässt. Einmal
  je Datei steht der zugehörige öffentliche Ausweis darin; er ist von uns
  ausgestellt und nennt Lizenznehmer, Kennung und Zahl der Plätze. Damit
  lässt sich später zeigen, **aus welcher Lizenz** eine Zeile stammt – ohne
  Netz und ohne Rückfrage. Bisher gab es dafür nur die Streuwertkette: Sie
  beweist, dass in der Datei nichts verschoben wurde, aber nichts über die
  Herkunft; wer sie nachrechnen kann, kann sie auch neu bauen. Das
  Protokollfenster prüft beides beim Öffnen und nennt den Halter, der CSV-
  Export führt Lizenzart, Kennung, Halter und Unterschrift als eigene
  Spalten. Zeilen aus dem Testzeitraum und aus der Zeit davor bleiben ohne
  Unterschrift – das ist kein Mangel und wird auch nicht als solcher
  gemeldet.

- **Beim ersten Start wird einmal gefragt: privater Rechner oder Betrieb?**
  Die Antwort ändert **nichts** am Funktionsumfang – Erkennung,
  Testzeitraum und Freistufe sind in beiden Fällen dieselben. Sie
  entscheidet nur, welche Lizenz die richtige ist. Damit steht die Frage
  auf jedem System gleich, auch dort, wo es keine Domänenerkennung gibt
  (macOS, Linux) – und eine Erklärung wiegt ohnehin schwerer als eine
  Erkennung. Änderbar unter *Mehr Einstellungen → Dieser Rechner*, für
  Firmen vorgebbar über `vorgaben.json`.
- **Die Platzzahl steht oben rechts**: „Firmenlizenz für Muster GmbH ·
  3/10 Plätze". Die Gesamtzahl kommt aus dem Lizenzschlüssel und braucht
  kein Netz; die belegte aus einer stillen Prüfung, die höchstens einmal
  am Tag läuft und nur bei gekaufter Lizenz. Sind **mehr** Plätze belegt
  als gekauft, wird die Zeile rot und verweist auf die Verwaltung – voll
  ist dagegen normal und bleibt ruhig.
- **Eine gesperrte Lizenz führt zum Rückfall auf die Freistufe, nicht zum
  Stillstand.** Das Programm arbeitet weiter und sagt einmal, warum. Ein
  Werkzeug, das mitten in der Arbeit dichtmacht, hilft niemandem – auch
  dem nicht, der es gesperrt hat. Wird die Sperre aufgehoben, holt die
  nächste Prüfung die Lizenz zurück. Netzfehler bleiben folgenlos.
- **Oben rechts steht jetzt, welche Art Lizenz läuft**: „Privatlizenz für …"
  bzw. „Firmenlizenz für …" statt nur „Lizenziert für …". Gehört ein Rechner
  zu einer Firmendomäne und läuft dort eine Privatlizenz, steht es in
  Warnfarbe mit dem Zusatz „dieser Rechner gehört zu einer Domäne".
- **Beim Einlesen einer Privatlizenz auf einem Domänenrechner erscheint ein
  Hinweis**: „Privat" gilt für die private Nutzung; im Firmeneinsatz braucht
  es eine Firmenlizenz. **Gesperrt wird nichts** – die Domänenerkennung kann
  im Einzelfall danebenliegen (ein Freiberufler in der Domäne seines Kunden),
  und niemand soll nach dem Kauf vor einer verschlossenen Tür stehen. Wer
  „Trotzdem verwenden – das ist mein privater Rechner" wählt, arbeitet
  weiter. Erkannt werden der klassische Domänenbeitritt und der
  Entra-Beitritt; eine Entra-**Registrierung** zählt bewusst nicht – wer
  sein dienstliches Konto auf dem privaten Rechner einrichtet, bleibt
  Privatanwender.
- **Auf einem Terminalserver zählt jeder Anwender als eigener
  Arbeitsplatz.** Zwanzig Leute an einem Server brauchen zwanzig Plätze –
  genau wie zwanzig Leute an zwanzig Schreibtischen. **Die eigene
  Server-Lizenz entfällt damit**, und mit ihr eine Sperre: Bisher lief auf
  einer Windows-Server-Ausgabe ohne Server-Freischaltung **gar nichts** –
  weder Testzeitraum noch Freistufe. Jetzt läuft dort alles wie überall; im
  Fenster steht nur der Hinweis „Terminalserver: je Anwender ein Platz".
  Die zwei freien Bereinigungen im Monat teilen sich weiterhin alle
  Anwender **einer Installation** – die zählt der Rechner, nicht der
  Anwender.
- **Das Prüfprotokoll gehört zur Firmenlizenz** und zum Testzeitraum. Mit einer Privatlizenz wird nichts
  geschrieben – wer privat arbeitet, hat keine Nachweispflicht.
  **Gelesen wird weiterhin immer**: Was einmal geschrieben wurde, lässt sich
  auch nach dem Ablauf einer Lizenz aufschlagen, auf die Kette prüfen und
  als CSV ausführen. Ein Nachweis, den man nicht mehr aufschlagen kann, wäre
  keiner.

  **Die Erkennung bleibt in allen Stufen dieselbe.** Es gibt keine Lizenz,
  die schlechter findet – begrenzt ist die Menge, nie die Qualität.
- **Wer eine Erkennung zurückholt, wird nach dem Grund gefragt**: vier zum
  Anklicken statt eines Freitextfelds – **Fehlalarm**, **eigene Firma**,
  **bereits anonym** und **bewusst behalten**. Bisher kannte die Anwendung
  die Handlung, aber nicht ihren Grund; für ein Haus mit Nachweispflicht ist
  das der Unterschied zwischen „wir haben geschwärzt" und „wir können
  nachweisen, was wir warum stehen gelassen haben". Der Grund steht im
  selben Fenster wie die Frage nach der Regel, nicht in einem zweiten
  Dialog, und bleibt bei der entstandenen Ausnahme stehen – so ist ein Jahr
  später nachvollziehbar, warum sie einmal angelegt wurde. Bei einer
  Sammelrücknahme wird **einmal** gefragt, nicht zwölfmal.

  **„Bewusst behalten" legt keine Dauerregel an**, und das ist der Kern:
  Dieser Grund sagt, dass die Angabe sehr wohl personenbezogen ist und
  trotzdem stehen bleibt, weil das Dokument sie braucht. Eine stehende
  Ausnahme daraus räumte den Schutz für alle künftigen Dokumente ab –
  deshalb wird die Regelleiter dann gesperrt statt bloß abgeraten.
  Vorbelegt ist ohnehin „Nur dieses Mal": Wer den Dialog mit der
  Eingabetaste wegklickt, legt nichts an.

  Läuft im Haus das **Prüfprotokoll**, entsteht dabei eine Zeile mit dem
  Ausgang „übersteuert" – Art, Anzahl, Grund und ob eine Dauerregel daraus
  wurde. Der zurückgeholte Wert steht auch dort nicht: Er ist genau der
  Klartext, den die Bereinigung entfernen sollte. Ein Freitextfeld gibt es
  aus demselben Grund nicht.
- **Der zuletzt gezogene Rahmen bleibt greifbar**: Er wirkt weiterhin sofort
  beim Loslassen – nichts wird langsamer –, bleibt danach aber mit Griffen
  an Ecken und Kanten stehen. Wer eine Kante anfasst und zieht, nimmt die
  erste Fassung still zurück und wendet die berichtigte an; die Pfeiltasten
  verschieben ihn um einen Bildpunkt, mit Umschalt ändern sie die Größe.
  Sitzt der Balken einen halben Buchstaben daneben, ist das **eine
  Bewegung** statt Rückgängig, neu zielen, neu ziehen. Im Verlauf steht
  danach trotzdem nur **ein** Schritt: Rückgängig führt vor den Rahmen und
  nicht zu seiner ersten, danebengegangenen Fassung. **Esc** lässt ihn los,
  der nächste Rahmen ebenso.
- **Das Panel „In dieser Datei ersetzt" hat ein Filterfeld und lässt
  mehrere Zeilen auf einmal auswählen**: Bei einem Verzeichnis mit
  dreihundert Namen ist die Liste sonst ein Heuhaufen. Wer merkt, dass eine
  ganze Art danebenlag – alle „Orte" waren in Wahrheit Firmennamen –, holt
  sie in einem Zug zurück; Rückgängig nimmt sie ebenso gemeinsam wieder
  weg. Gezählt und gestrichen wird dabei nur, was wirklich zurückgeholt
  wurde: Ein Wert, der so gar nicht im Dokument steht, bleibt in der Liste
  stehen.
- **Die Seitenzahl ist ein Eingabefeld** – Zahl eintippen, Eingabetaste,
  fertig. Bei Seite 3 von 60 ist Blättern kein Weg. Dazu bedient die
  Tastatur die Seite wie in jedem Betrachter: **Bild↑/Bild↓** rollen und
  blättern am Seitenrand von selbst weiter (nach unten fängt die neue Seite
  oben an, nach oben unten), **Strg+Pos1/Strg+Ende** springen an den Anfang
  und ans Ende des Dokuments.
- **Seitenminiaturen im Nachbessern-Fenster**: Links liegt ein Fach mit
  kleinen Abbildern aller Seiten – ein Klick blättert hin, die aktuelle
  Seite ist markiert. Bei einem dreißigseitigen Scan ist „◀ ▶" kein Weg:
  Einer Seitenzahl sieht man nicht an, welche Seite gemeint ist, dem Bild
  schon. Das Fach lässt sich zuklappen (Ansicht → „Seitenminiaturen
  anzeigen") und erscheint nur, wo es etwas zu zeigen gibt – nicht bei
  einer einzelnen Seite, einem Bild oder einem Textdokument.
- **Das Fenster kommt wieder, wie Sie es verlassen haben**: Größe und Platz,
  die Anordnung der Fächer und die zuletzt gewählte Zoomart („Seite" oder
  „Breite") gelten beim nächsten Öffnen weiter. Wer immer auf Seitenbreite
  arbeitet, stellt das einmal ein und nicht bei jeder Datei.
- **Suchen im Nachbessern-Fenster (Strg+F)**: Eine Suchleiste unten am
  Dokument – Begriff eintippen, und alle Fundstellen leuchten gelb auf, die
  gerade angesteuerte orange; der Zähler sagt „3 von 12". Mit F3 und
  Umschalt+F3 (oder ◀ ▶) geht es weiter, über Seitengrenzen hinweg – bei
  einem PDF blättert die Suche selbst dorthin. Sie versteht auch Wortfolgen
  über mehrere Wörter („Ingeborg Falkenstein") und lässt sich auf
  Groß-/Kleinschreibung stellen. Das ist mehr als Bequemlichkeit: Es ist die
  **Gegenprobe** – „steht der Name wirklich nirgends mehr?". Im Text
  markiert die Suche den Fund gleich, sodass „Auswahl ersetzen" direkt
  darauf zugreift; über „Original zeigen" lässt sich derselbe Begriff im
  Original und im Ergebnis vergleichen.
- **Ein Fehlerbericht sagt jetzt, worum es geht**: Im Meldedialog wählen Sie
  die Art – „Etwas wurde übersehen", „Etwas wurde zu viel geschwärzt",
  „Programmfehler oder Absturz", „Frage zur Lizenz", „Wunsch oder Anregung",
  „Sonstiges". Nach einem Absturz ist das schon richtig vorbelegt. Danach
  richtet sich, wie dringend Ihre Meldung bearbeitet wird: **Eine übersehene
  Angabe hat immer Vorrang** – auch aus der kostenlosen Fassung und auch vor
  dem Wunsch eines Firmenkunden.
- **Mit gekaufter Lizenz werden Meldungen zügiger bearbeitet**: Das Programm
  schickt dafür einen **Prüfwert** Ihres Lizenzschlüssels mit – nicht den
  Schlüssel. Aus dem Prüfwert lässt sich der Schlüssel nicht zurückrechnen,
  und nach der Zuordnung wird er verworfen; gespeichert wird nur, ob es eine
  Firmen- oder Einzellizenz war. Testzeitraum und kostenlose Fassung senden
  ihn gar nicht – und werden deswegen nicht nachrangig behandelt.
- **Prüfprotokoll für Häuser mit Nachweispflicht**: Die Verwaltung kann ein
  Protokoll einschalten, das je Bereinigung eine Zeile festhält – Zeitpunkt,
  Datei, Anzahl und **Arten** der Fundstellen, Sprache, Erkennungsstufe,
  Warnungen. Abbruch und Fehler bekommen ihre eigene Zeile: Ein Nachweis, der
  nur die geglückten Läufe kennt, ist keiner.
  **Voreingestellt ist es aus** und entsteht nie von selbst. Es enthält
  **keine Fundwerte**, und der Dateiname steht vorgabegemäß nur als Streuwert
  darin. Jede Zeile trägt den Streuwert der vorherigen, sodass nachträgliches
  Ändern auffällt. Eingeschaltet wird es über die Vorgabendatei
  (`"protokoll": true`); Einzelheiten im Handbuch, samt des Absatzes zur
  Mitbestimmung – mit `"protokoll_anwender": false` bleibt der Nachweis und
  entfällt die Auswertbarkeit über Beschäftigte.
  Angesehen wird es unter „Programm → Prüfprotokoll …": Monat wählen, Zeilen
  lesen, **Kette prüfen** („3 Zeilen, unverändert" oder „bricht bei Zeile 7"),
  als CSV für den Prüfer ausgeben. Der Menüpunkt erscheint nur, wo es etwas
  anzusehen gibt. **Auswertungen je Person gibt es bewusst nicht** – wir
  liefern eine Liste und einen Export, keine Ranglisten.
- **Ordner durchsehen, ohne etwas zu verändern**: Unter „Datei → Ordner
  durchsehen …" (oder `maskuro <ordner> --suchlauf --rekursiv`) sieht das
  Programm nach, **wo** personenbezogene Daten liegen – Datei, Art, Anzahl.
  Es entsteht keine Ergebnisdatei, keine Arbeitskopie, gar nichts; gelesen
  wird, gezählt wird, mehr nicht. Für einen Datenschutzbeauftragten ist das
  der Schritt vor jeder Bereinigung.
  Der Bericht nennt **keine Fundwerte** – er wäre sonst selbst eine Sammlung
  personenbezogener Daten. Und er sagt, was er *nicht* wissen kann: Dateien,
  aus denen kein Text zu lesen war (ein Scan ohne Textebene), stehen in einem
  eigenen Abschnitt – dort heißt „null Funde" *nichts gelesen*, nicht
  *nichts enthalten*.
- **Zwei neue Arten: Alter und Sendungsnummer.** Das **Alter** („67 Jahre
  alt", „42-jährig", „Alter: 35") ist eine indirekte Angabe, die bisher durch
  jede Erkennung fiel – zusammen mit Beruf und Wohnort bezeichnet sie in
  einer kleinen Gemeinde genau eine Person. Entfernt wird nur die Zahl, der
  Satz bleibt lesbar. Die **Sendungsnummer** ist ein Schlüssel zum
  Sendungsverlauf beim Zusteller und damit zu einer Anschrift; erkannt wird
  sie hinter einer Beschriftung („Sendungsnummer:", „Paket-Nr.") sowie in der
  unverwechselbaren UPS-Form.
- **Datumsangaben verschieben statt ersetzen**: Für Kranken- und
  Gerichtsakten ist die Chronologie der Inhalt – `[DATUM_1]` zerstört sie.
  Die Strategie **verschieben** rückt alle Datumsangaben um denselben Betrag:
  „drei Tage später" bleibt drei Tage später, der echte Termin ist weg. Der
  Betrag ist über alle Dateien eines Vorgangs derselbe, sonst nützte es
  nichts. Verschoben wird nur, was sicher als Datum gelesen werden kann –
  „im Frühjahr" oder eine Uhrzeit bekommen weiter einen Platzhalter, denn
  ein geratenes Datum sähe echt aus. **Und der Bericht sagt es**: Ein
  verschobenes Datum ist kein Nachweis über Zeitpunkte.
- **Je Art festlegen, was geschieht**: Nicht jeder Fund will denselben
  Platzhalter. Im Reiter **Platzhalter** lässt sich für einzelne Arten
  einstellen, dass sie stattdessen **geschwärzt** (ersatzlos entfernt),
  **maskiert** (`**.**.****` – die Form bleibt, der Inhalt geht) oder
  **gehasht** werden. Beim Hashen bekommt derselbe Wert dieselbe Kennung –
  auch in fünf verschiedenen Schriftstücken, und ohne dass sich daraus der
  Wert zurückrechnen ließe. Voreingestellt bleibt alles beim nummerierten
  Platzhalter; die Liste enthält nur die Abweichungen.
  Beim Maskieren bleibt **nichts** sichtbar: Die letzten Stellen einer
  Kontonummer sind genau der Teil, an dem sie wiedererkannt wird. Wer sie
  für einen Abgleich braucht, schreibt in der Regeldatei `maskieren:4`.
- **Die Platzhalter lassen sich selbst gestalten**: Unter
  „Erkennungsregeln und eigene Begriffe …" gibt es den Reiter
  **Platzhalter**. Dort steht, wie das aussieht, was an die Stelle eines
  gefundenen Werts tritt – die Vorgabe bleibt `[NAME_1]`, aber auch
  `<NAME-1>` oder `((NAME 1))` ist möglich. Beim Tippen steht darunter, wie
  es im Dokument aussehen wird.
- **Beschriftungen in der Sprache des Dokuments, nicht der Oberfläche**:
  Bisher stand in jedem bereinigten Schriftstück `[TELEFON_1]`, auch bei
  englischer Bedienung. Jetzt ist die Sprache der Beschriftungen wählbar
  (`[PHONE_1]`) – und sie hängt bewusst **nicht** an der Oberflächensprache,
  damit ein Wechsel der Bedienoberfläche nicht rückwirkend andere Ergebnisse
  erzeugt. Die Einstellung gehört zu den Regeln und wandert damit auch in
  die firmenweite Regeldatei: Eine Kanzlei legt einmal fest, wie ihre
  bereinigten Schriftstücke aussehen.
- **Was die Anwendung gelernt hat, steht jetzt in einer Liste**: Unter
  „Erkennungsregeln und eigene Begriffe …" gibt es den Reiter **Ausnahmen**.
  Dort steht, was beim Nachbessern zurückgeholt und künftig stehen gelassen
  werden soll – bisher entstanden diese Einträge zwar, waren aber nirgends zu
  sehen und damit auch nicht zurückzunehmen.
- **Ausnahmen für ganze Nummernkreise**: Wer eine Artikel- oder Prüfnummer
  zurückholt, kann statt der einen Nummer die ganze **Form** stehen lassen
  („nichts, was aussieht wie ART-4711"). In einer Ersatzteilliste ist das der
  Unterschied zwischen einem Klick und zweihundert. Die Regel greift nur,
  wenn sie den **ganzen** Treffer abdeckt – ein Name daneben bleibt
  geschützt –, und angeboten wird sie nur für Werte mit erkennbarer Form:
  aus einem Wort wie „Techniker" wird nie ein Muster.
- **Regeln exportieren und importieren**: Zwei Knöpfe im selben Fenster
  schreiben alle Listen – Begriffe, Suchmuster und Ausnahmen – in eine Datei
  und lesen sie auf einem anderen Rechner wieder ein, wahlweise dazunehmend
  oder ersetzend. Es ist dasselbe Format wie die firmenweite Regeldatei: Was
  ein Arbeitsplatz sich erarbeitet hat, kann die Verwaltung unverändert für
  alle hinterlegen.
- **Fehler melden, ohne die Protokolldatei suchen zu müssen**: Unter
  „Hilfe → Fehler melden" entsteht ein Bericht mit Fassung, Betriebssystem,
  Erkennungsstufe und – auf Wunsch – den letzten Zeilen des Protokolls.
  **Vor dem Senden steht der vollständige Bericht im Klartext im Fenster**;
  was Sie dort nicht lesen, geht auch nicht hinaus. Dateinamen und Pfade
  werden vorher auf ihre Endung eingedampft („…\Angebot Musterbau GmbH.pdf"
  wird zu `<datei>.pdf`), ebenso E-Mail-Adressen und Kontonummern im Text.
  **Dokumentinhalte werden nie übertragen, und es gibt kein Feld für
  Anhänge** – ein Warntext daneben hätte das nicht verhindert, das Feld
  selbst ist die Einladung. Wer eine Antwortadresse einträgt, bekommt eine
  Antwort; ohne sie eine Ticketnummer. Firmen können den Weg zentral
  schließen.
- **Nach einem Absturz wird gefragt, nicht gesendet**: Endet Maskuro
  unerwartet, wird der Vorfall örtlich vermerkt und Ihnen angeboten – sofort,
  und falls das nicht mehr geht, beim nächsten Start. Auch dieser Bericht
  wird vorher vollständig angezeigt. Es gibt weiterhin **keine Telemetrie
  und keinen selbsttätigen Absturzbericht**.
- **„Wunsch äußern" führt zur öffentlichen Wunschliste** – ein Fehler
  braucht einen Zustand, ein Wunsch braucht Sichtbarkeit.
- **„Von Hand schwärzen …" steht jetzt neben „Bereinigen"**: Der Weg, eine
  Datei ohne jede Erkennung zu öffnen und selbst zu schwärzen, war bisher nur
  über das Menü erreichbar – jetzt steht er dort, wo man ihn wählt: als
  zweiter Weg zu beginnen. Er nimmt auch, was schon in der Liste liegt
  (markierte Zeilen, sonst alle); der Dateidialog kommt nur noch bei leerer
  Liste. Eine bereits bereinigte Datei wird dabei weitergeführt statt neu
  begonnen – vorher hätte ein zweiter Aufruf die schon geschwärzte
  Ergebnisdatei stillschweigend mit dem Original überschrieben.
- **„Nachbessern …" unten ist weggefallen**: Nachbessern gehört zu **einer**
  fertigen Datei; der Knopf unten konnte nur raten, welche gemeint ist. Der
  Stift in der Zeile trifft es genau.

### Geändert

- **Handbuch und FAQ kennen den neuen Editor**: Sie beschrieben noch die
  Werkzeugspalte links, die es seit dem Umbau nicht mehr gibt. Jetzt stehen
  dort Menüzeile, Symbolleiste, Statuszeile, Reiter und F1 für alle Kürzel,
  dazu die Seitenminiaturen, der greifbare Rahmen, Filter und
  Mehrfachauswahl im Trefferpanel – und vor allem **Suchen als
  Gegenprobe**: In einem Programm, das Angaben entfernt, ist Strg+F keine
  Bequemlichkeit, sondern die Antwort auf „steht der Name wirklich nirgends
  mehr?". Dafür gibt es auch einen eigenen FAQ-Eintrag. Zwölf Sprachen.
- **Das Nachbessern-Fenster sieht aus und lässt sich bedienen wie ein
  Dokumentprogramm**: Es hat jetzt eine **Menüzeile** (Datei, Bearbeiten,
  Werkzeuge, Ansicht, Hilfe), in der jede Handlung mit Namen und
  Tastenkürzel steht, eine **Symbolleiste** mit Bild *und* Wort, eine
  **Statuszeile** mit Seitenzahl, Zoomregler und Zoomstufe rechts unten und
  ein **Panel „In dieser Datei ersetzt"**, das sich zuklappen oder auf die
  andere Seite ziehen lässt (zurück über Ansicht → „Ersetzte Werte
  anzeigen"). Mehrere geöffnete Dateien liegen als **Reiter** über der
  Seite statt in einer Auswahlliste. Die üblichen Tastenkürzel gelten:
  Strg+S und Strg+Umschalt+S zum Speichern, Strg+Z und Strg+Y für
  Rückgängig und Wiederholen, Strg+H für „Auswahl ersetzen",
  Strg++/Strg+− für den Zoom, Strg+0 für die ganze Seite, Strg+1 für die
  Seitenbreite, Strg+Bild↑/Bild↓ zum Blättern, Strg+F4 zum Schließen; F1
  zeigt sie alle. Dazu drei Mausgriffe, die man
  aus jedem Betrachter kennt: **mittlere Maustaste** schiebt die Seite,
  **Rechtsklick** öffnet die Werkzeuge dort, wo gearbeitet wird, und
  **Esc** verwirft einen angefangenen Rahmen, bevor er wirkt. Der Knopf
  „Fertig" ist entfallen – geschlossen wird über Datei → Schließen oder das
  Fensterkreuz, wie überall sonst.
- **Rückgängig hat ein Gegenstück bekommen**: **Wiederholen** (Strg+Y) holt
  einen zurückgenommenen Schritt wieder her – bis zu zehn Schritte in beide
  Richtungen. Bisher war Rückgängig eine Einbahnstraße: Wer einmal zu weit
  zurückging, musste die Arbeit noch einmal machen. Wie überall gilt: Sobald
  Sie nach einer Rücknahme etwas Neues tun, ist der zurückgenommene Zweig
  weg – eine Aktion, die nichts gefunden hat, kostet ihn aber nicht.
- **Von Hand schwärzen legt erst auf Klick eine Datei an**: Wer eine Datei
  nur von Hand schwärzt, arbeitet an einer flüchtigen Kopie – neben dem
  Original entsteht nichts mehr, solange nicht gespeichert wird. Bisher lag
  die Ergebnisdatei ab dem Öffnen im Ordner des Originals und wuchs mit jedem
  Balken mit; wer nur nachsehen wollte, hatte damit schon eine Datei erzeugt,
  und das sah aus wie ein überschriebenes Original. Im Nachbessern-Fenster
  gibt es dafür jetzt **Speichern** (in den Ordner des Originals, unter dem
  üblichen Ergebnisnamen) und **Speichern unter …** (an einen selbst
  gewählten Ort). Eine vorhandene Datei gleichen Namens bleibt stehen, das
  Original lässt sich auch im Dateidialog nicht überschreiben, und wer mit
  ungespeicherter Arbeit schließt, wird gefragt. Ergebnisse eines
  Bereinigungslaufs bleiben unverändert: Sie liegen schon als Datei vor, dort
  wirkt jede Aktion weiterhin sofort.
- **Die Änderungsliste ist eine Seite statt eines Dutzends**: Im Hilfefenster
  stand bisher jede Fassung als eigenes Thema in der Liste links – nach
  einigen Freigaben bestand die Hälfte der Liste aus Datumszeilen, und die
  eigentlichen Hilfethemen gingen darin unter. Jetzt gibt es den einen
  Eintrag „Änderungen"; darunter stehen alle Fassungen untereinander, die
  neueste oben. Die Suche geht damit über den ganzen Verlauf statt über eine
  Fassung.
- **Es gibt nur noch eine Oberfläche**: Seit dem Umstieg lief die neue
  Fassung neben der alten her, erreichbar über den Schalter `--tk`. Nachdem
  sie unter Windows und macOS im Alltag bestanden hat, ist die alte
  entfallen. Für die Anwendung ändert sich nichts – wer `--tk` in einer
  Verknüpfung stehen hat, bekommt weiterhin das Programm und keine
  Fehlermeldung. Das Paket wird dadurch kleiner, und unter Linux braucht es
  kein `python3-tk` mehr.
- **Handbuch und FAQ beantworten die Frage nach der ganzen Akte**: „Wie
  sorge ich dafür, dass `[NAME_1]` in fünf Dateien dieselbe Person ist?" Die
  Antwort – die Strategie **hashen**, die die Kennung aus dem Wert ableitet
  statt aus einer je Datei neu beginnenden Nummer – gab es schon, sie stand
  aber nur als eine Zeile unter fünf Strategien. Jetzt hat sie einen eigenen
  Eintrag in zwölf Sprachen, samt dem, was dazugehört: Über mehrere
  Arbeitsplätze hinweg gilt sie nur mit derselben Regeldatei, beim Einlesen
  mit „Dazunehmen" bleibt absichtlich die eigene, und eine gleichbleibende
  Kennung macht dieselbe Person über alle Dateien hinweg verfolgbar.

- **Der Testzeitraum hält auf Mac und Linux, was er unter Windows schon
  hielt.** Es gibt dort jetzt eine Marke außerhalb des Benutzerprofils –
  bisher war ein zweites Benutzerkonto auf demselben Rechner ein frischer
  Testzeitraum, während Windows über `ProgramData` längst dagegenhielt.
  Fehlt das Schreibrecht, fällt es lautlos aus; ohne Adminrechte
  unbrauchbar zu sein wäre der schlechtere Tausch. Bestehende
  Testzeiträume ziehen mit um und werden nicht zurückgesetzt.

### Behoben

- **Die Frage „Privat oder im Betrieb?" kam bei jedem Start.** „Später"
  hieß in Wahrheit „beim nächsten Start wieder" – die Frage ließ sich also
  gar nicht wegklicken. Jetzt wird sie einmal gestellt; wer „Später"
  wählt, wird nicht wieder gefragt. Die Wahl steht weiterhin unter *Mehr
  Einstellungen → Dieser Rechner*.
- **Gesichter wurden auf einem frischen Rechner nicht verpixelt.** Der
  Haken „Gesichter unkenntlich" war beim Aufbau des Fensters an, wurde
  aber unmittelbar danach beim Laden der Einstellungen wieder auf aus
  gesetzt – auf jedem Rechner ohne eigene Wahl. Wer ein Foto-Verzeichnis
  bereinigte, bekam geschwärzte Namen und scharfe Portraits, also genau
  den Fall, für den es den Schalter gibt. Jetzt ist er voreingestellt an;
  wer ihn abwählt, dessen Wahl bleibt wie bisher gemerkt.
- **Der Aufruf über die Kommandozeile startete gar nicht mehr.** Beim
  Entfernen der Server-Sperre war ein Bruchstück des alten Blocks
  stehengeblieben; die Datei ließ sich seitdem nicht mehr laden. Betroffen
  war nur der Kommandozeilenweg – Fenster, Kontextmenü und
  Zwischenablage-Wächter liefen weiter.
- **Das Trefferpanel zeigte Zeilen, die im Dokument nicht vorkamen**: In
  einem PDF ist ein Platzhalter fast immer länger als das, was er ersetzt –
  in „ist 77 Jahre alt" war neben der Zahl kein Platz für „[ALTER_1]", also
  wurde die Stelle geschwärzt. Die Zuordnung behauptete trotzdem
  `77 → [ALTER_1]`: Ein Klick auf diese Zeile markierte nichts,
  Zurücknehmen ging nicht, und niemand erfuhr, warum. Jetzt hält die
  Zuordnung fest, **was wirklich geschah** – im Panel steht dort
  „geschwärzt – kein Platz", die Zeile ist gedämpft, ein Klick erklärt sich
  in der Statuszeile, und der Bericht sagt nach dem Lauf, wie oft es
  vorkam. Wer die Platzhalter braucht, macht sie kürzer: `<N1>` passt, wo
  `[ALTER_1]` nicht mehr hinpasst.

  **Dasselbe von der anderen Seite** bei den Strategien ohne Platzhalter:
  Wer schwärzen lässt, bekam eine Zeile mit leerer zweiter Spalte, wer
  maskieren lässt, eine mit `**`. Jetzt steht dort „entfernt" bzw.
  „maskiert", und ein verschobenes Datum zeigt beides: das neue Datum
  **und** dass es verschoben ist – ohne diesen Zusatz liest es sich wie ein
  echtes.
- **Ein Platzhalter konnte über den Seitenrand hinauslaufen**: Stand eine
  Angabe ganz am rechten Rand, endete „[KENNNUMMER_1]" im Ergebnis als
  „[KENNNUMME" an der Papierkante – und in einem gerasterten Ergebnis war
  das nicht mehr zu retten. Jetzt hält der Platzhalter Abstand zur Kante;
  wo er dadurch nicht mehr lesbar hineinpasst, wird geschwärzt, und der
  Bericht sagt es.
- **Eine große Textdatei ließ sich nicht abbrechen**: Der Textweg (Text,
  Markdown, CSV) fragte als einziger nie nach, ob abgebrochen wurde. Bei
  einer kurzen `.txt` fiel das nicht auf; bei einer großen CSV lief die
  Erkennung über hunderte Blöcke, und der Abbruchknopf wartete bis zum
  Ende. Jetzt wird zwischen den Blöcken gefragt – und ein Abbruch
  hinterlässt wie überall keine halbe Ergebnisdatei.
- **Auf hochkant eingescannten Seiten riss ein geschwärztes Wort die ganze
  Zeile mit**: Wer in einem gedrehten Scan – Seite quer aufgenommen, im
  Betrachter aufrecht gestellt – ein einziges Wort schwärzte oder ersetzte,
  verlor den auslesbaren Text der übrigen Zeile. Sichtbar blieb sie, nur
  ließ sich nichts mehr davon anfassen: Der Rest des Satzes war weder zu
  schwärzen noch zu ersetzen, weil es dort für das Programm nichts mehr
  gab. Jetzt fällt genau das Wort, das gemeint war. Bei **schräg**
  gesetztem Text (kein rechter Winkel) bleibt es beim bisherigen,
  vorsichtigen Verhalten – dort ließe sich die Lage nicht genau genug
  zurückrechnen.
- **Im Fenster „Bilder festlegen" blieb der Mauszeiger eine Sanduhr**: Sie
  gehört zum Einsammeln der Bilder davor und stand danach über dem ganzen
  offenen Fenster, in dem niemand wartet.
- **Entfernte Dateien nahmen ihre Bildentscheidungen nicht mit**: Wer eine
  Datei aus der Liste warf und wieder hinzufügte, arbeitete unbemerkt mit
  den alten Einzelentscheidungen weiter. Jetzt gilt wieder der Vorschlag
  aus dem Auswahlfeld, bis man erneut einzeln festlegt.
- **Kein Symbol im Infobereich, wenn der Symbolordner leer war**: Das
  Fenster holte sich seines längst aus dem Quellbaum, die Taskleiste blieb
  stumm leer. Beide suchen jetzt an denselben Stellen.
- **Meldungen aus dem Infobereich trugen kein Programmsymbol**: Sie kamen
  mit dem allgemeinen Hinweiszeichen des Systems und sahen nach niemandem
  aus.
- **Im Fehlerbericht verschwand der halbe Satz**: Stand hinter einem
  Dateinamen ein Komma – „… Weber.pdf, Rückfragen an …" –, ersetzte die
  Säuberung nicht nur den Pfad, sondern alles bis zum nächsten Punkt weiter
  hinten im Text. Übrig blieb „Datei war `<datei>.de`". Es ging dabei nie zu
  wenig hinaus, sondern zu viel – aber der Bericht verlor genau die Angaben,
  wegen derer man ihn schreibt.
- **Eine gesperrte Adresse sah aus wie eine abgelehnte Lizenz**: Filtert ein
  Firmennetz `maskuro.com` heraus, antwortet nicht der Lizenzdienst, sondern
  das Sicherheitsgerät – mit einer Sperrseite. Das Programm las daraus, der
  Dienst habe den Schlüssel abgelehnt, und zeigte einem zahlenden Kunden ein
  Fenster mit leerer Begründung. Jetzt gilt: Wer nicht in der erwarteten Form
  antwortet, ist nicht der Lizenzdienst – dann wurde **nichts gelernt**, es
  wird weitergearbeitet und kein Fenster gezeigt. Eine echte Absage des
  Dienstes (gesperrt, abgelaufen, Plätze voll) wirkt unverändert.
- **Hilfeseiten brachen mitten im Satz ab**: Stand in einem Text eine spitze
  Klammer – etwa der Platzhalter `<datei>.pdf` –, hielt die Anzeige sie für
  eine Anweisung und verschluckte alles danach. Betroffen waren Handbuch,
  FAQ, Änderungsliste und die Rechtstexte gleichermaßen. Spitze Klammern
  stehen jetzt einfach da, wo sie stehen.
- **Der Datenschutzhinweis kannte die Lizenz-Anmeldung gar nicht**: Er zählte
  die Verbindungen nach außen auf – und ließ dabei ausgerechnet die aus, bei
  der etwas übertragen wird. Die Anmeldung eines Arbeitsplatzes steht jetzt
  dort, mit allen fünf übertragenen Angaben, dem Hinweis auf den Knopf „Was
  wird übertragen?" und darauf, dass Testzeitraum und Freistufe überhaupt
  nichts anmelden. Ebenso der neue Fehlerbericht. In allen zwölf Sprachen.
- **„Es überträgt nichts an den Hersteller" war zu weit gefasst**: Für Ihre
  Dokumente stimmt der Satz unverändert – für eine freiwillig eingetragene
  Antwortadresse nicht. Datenschutzhinweis und FAQ sagen jetzt genau, was den
  Hersteller erreicht und auf welcher Rechtsgrundlage.
- **Das Symbol im Infobereich war verwaschen**: Auf Bildschirmen mit
  Skalierung – also fast allen – wurde nicht die für kleine Größen gezeichnete
  Fassung gezeigt, sondern die feine, zweimal hintereinander verkleinert. Bei
  125 % kam ein 32er Bild erst auf 25 und dann auf 20 Bildpunkte herunter; die
  beiden Balken verschwammen zu einem grauen Klotz. Das Symbol wird jetzt in
  genau der Größe eingesetzt, in der Windows es zeigt, und die Symboldatei
  bringt diese Größen für alle üblichen Skalierungen mit. Wechselt die
  Skalierung im laufenden Betrieb, wird das Symbol neu geholt.

- **„Ordner öffnen" führte bei gemischten Ordnern irgendwohin**: Der Knopf
  unten zeigte immer den Ordner der zuletzt fertigen Datei – bei Dateien aus
  verschiedenen Ordnern also einen von mehreren, ohne zu sagen, welchen. Er
  ist weg; zum Ergebnis führt das Ordner-Symbol in der jeweiligen Zeile, und
  *Datei → Ordner öffnen* folgt jetzt der Auswahl in der Liste.

- **Gelernte Ausnahmen gingen beim Speichern der Regeln verloren**: Wer im
  Regelfenster auf „Übernehmen" klickte, löschte damit stillschweigend alles,
  was die Anwendung sich beim Nachbessern gemerkt hatte – die Liste stand in
  der Datei, aber in keinem Feld, und das Fenster schrieb sie leer zurück.
  Aus demselben Grund galten die firmenweiten Regeln danach bis zum nächsten
  Start nicht mehr.
- **Die Anwendung schlug Suchmuster vor, die keine sein durften**: Zu einem
  von Hand geschwärzten Namen wurde „alles in dieser Form" angeboten – für
  „Musterfrau" also jedes Wort aus zehn Buchstaben, für „4711" jede
  vierstellige Zahl. Ein Muster entsteht jetzt nur noch aus Werten, die
  wirklich eine Form haben: mit Ziffern und mit etwas anderem darin.
- **Die Änderungsliste unter „Hilfe & FAQ" endete bei 0.10.14**: Zu den
  Fassungen 0.10.15 und 0.10.16 stand dort nichts – ihre Einträge lagen
  weiterhin unter „Unveröffentlicht", obwohl beide längst ausgeliefert
  waren. Wer wissen wollte, was die eigene Fassung gebracht hat, fand sie
  gar nicht. Beide Abschnitte tragen jetzt ihre Nummer und ihr Datum.
- **„Schwärzen" und „Ersetzen" trugen dasselbe Symbol**: In der
  Werkzeugleiste des Nachbessern-Fensters war beides ein roter Balken über
  zwei Textzeilen – welcher Knopf welches Werkzeug war, verriet erst der
  Tooltip. „Ersetzen" zeigt jetzt einen roten Platzhalter mit „[A]" darin –
  in eckigen Klammern wie das, was im Dokument stehen bleibt („[NAME_1]").
  Beim Schwärzen bleibt ein schwarzer Balken, beim Ersetzen etwas Lesbares:
  genau das ist der Unterschied. „Auswahl ersetzen" trägt denselben
  Platzhalter – es geschieht ja dasselbe –, dazu die Griffe einer
  Textmarkierung: nicht ziehen, sondern das Markierte ersetzen.
- **Firmeneigene Feldbeschriftungen wurden als Namen geschwärzt**: „Name:",
  „Abteilung:" und „Sachbearbeiter:" kannte das Programm, aber jedes Haus
  hat eigene – „Prüfschritt:", „Anlagenteil:", „Losgröße:", „Zuständig:".
  Die verschwanden, und im Ergebnis war nicht mehr abzulesen, was in
  welchem Feld gestanden hatte. Von 22 gebräuchlichen Beschriftungen fielen
  fünf; jetzt keine.

  Der Sprecher im Protokoll bleibt davon unberührt: „Bauer: Ich stimme dem
  Vorschlag zu." ist ein Name und wird weiterhin entfernt. Genau daran wäre
  die einfache Regel gescheitert – „Wort vor Doppelpunkt gleich
  Überschrift" hätte ausgerechnet in Besprechungsprotokollen Namen stehen
  lassen, und eine übersehene Angabe wiegt schwerer als eine geschwärzte
  Überschrift.
- **„Sie verwenden die neueste Fassung" konnte eine Unwahrheit sein**: Ließ
  sich die gesicherte Verbindung zum Aktualisierungsserver nicht überprüfen,
  wertete das Programm das wie „nichts Neues gefunden" – und meldete
  Entwarnung, obwohl gar nicht nachgesehen werden konnte. Ausgerechnet über
  diesen Weg kommen Sicherheitskorrekturen. Jetzt wird gesagt, dass die
  Prüfung nicht möglich war, und **woran es meist liegt**: In Firmennetzen
  bricht oft ein Sicherheitsgerät den Datenverkehr auf. Ein Server, der
  gerade nicht erreichbar ist, bleibt weiterhin stillschweigend folgenlos –
  das geht von selbst vorbei, eine abgelehnte Zertifikatsprüfung nicht.
- **Eine Aktualisierung installierte Maskuro ein zweites Mal daneben**: Für
  Windows gibt es zwei Pakete – das gewöhnliche Setup und das MSI für die
  verwaltete Ausrollung. Welches die Aktualisierung nahm, hing bisher vom
  Zufall ab. Wechselte sie dabei das Format, entstand keine neue Fassung,
  sondern eine **zweite Installation**: zwei Einträge unter „Apps &
  Features", und weil beide denselben Ordner benutzen, riss das Entfernen
  der einen der anderen die Dateien weg. Die Aktualisierung bleibt jetzt
  bei dem Format, aus dem die vorhandene Installation stammt. Wer bereits
  zwei Einträge hat, entfernt den älteren und installiert die neuere
  Fassung noch einmal darüber.

---

## 0.10.16 – 11. August 2026

### Neu

- **Kennnummern werden an ihrer Beschriftung erkannt**: Steht im Dokument
  „Kundennummer: K903944", „Vertragsnummer: V10447483" oder
  „Aktenzeichen: 12/2026-AB", wird der Wert entfernt – ganz gleich, wie
  das Hausformat aussieht. Bisher musste man dafür ein eigenes Suchmuster
  hinterlegen. Die Beschriftung selbst bleibt stehen, damit im Ergebnis
  ablesbar ist, *was* dort entfernt wurde. Warennummern (Artikel-,
  Bestell-, Seriennummer) sind bewusst nicht dabei: Die bezeichnen eine
  Ware und stehen zu Tausenden in Katalogen.
- **Als IBAN beschriftete Kontonummern werden auch ohne gültige Prüfziffer
  entfernt**: Bisher entschied allein die Prüfsumme – und ausgerechnet
  eine IBAN mit Zahlendreher blieb dadurch stehen. Steht „IBAN:" davor,
  hat das Dokument die Frage schon beantwortet. Ohne Beschriftung bleibt
  es bei der Prüfsumme, damit nicht jede lange Ziffernfolge zur
  Bankverbindung wird.
- **Die Anwendung lernt aus dem Nachbessern**: Wer im Nachbessern-Fenster
  etwas von Hand entfernt, wird gefragt, ob das künftig selbst gefunden
  werden soll. Zur Wahl stehen drei Weiten – nur dieser Wert, alles hinter
  derselben Beschriftung („Kundennummer:“), oder alles derselben Form. Zu
  jeder steht **vorher**, wie viele Stellen sie im vorliegenden Dokument
  träfe, mit Beispielen: So verrät sich eine zu weit gefasste Regel, bevor
  sie gespeichert wird. Vorbelegt ist nichts, gefragt wird immer. Die Regel
  bleibt auf dem Rechner, wird bei jeder künftigen Bereinigung mitgesucht
  und lässt sich unter „Eigene Regeln“ wieder entfernen.
- **Und umgekehrt**: Wer eine Ersetzung zurücknimmt, wird gefragt, ob die
  Angabe künftig stehen bleiben soll – „Techniker" ist kein Name. Diese
  Leiter ist kürzer, weil eine Ausnahme Schutz **wegnimmt**: der wörtliche
  Begriff, und nur bei Werten mit erkennbarer Form („ART-0815") das Muster
  dazu – für ganze Nummernkreise, die sonst einzeln zurückgenommen werden
  müssten. Eine Sprosse „alles hinter dieser Beschriftung" gibt es hier
  bewusst nicht: Sie griffe ausgerechnet dort, wo Namen stehen. Sieht der
  Wert nach einem Namen aus, wird gar nichts angeboten.

### Behoben

- **Bei einem Scan sagt die Meldung jetzt, worauf es ankommt**: Bisher
  hieß es nur, die Seite sei „nicht geprüft“ – das stimmte seit dem
  Schwärzen im Bild nicht mehr und half auch nie weiter. Ist die
  Texterkennung aus, steht dort jetzt ausdrücklich, dass von einem Scan
  **nichts** geprüft wurde und dass sie bei Scans der wichtigste Schalter
  ist. Ist sie an, wird gesagt, dass auch sie Handschriftliches nicht
  findet – eine Unterschrift oder ein handschriftlich eingetragener Name
  bleibt stehen.
- **Gewöhnliche Wörter wurden als Namen geschwärzt**: Besonders in
  Sprachen ohne eigenes Namensmodell – Dänisch, Polnisch – hielt die
  Erkennung alltägliche Verben für Personen oder Orte. Ein Eigenname wird
  in allen unterstützten Sprachen groß geschrieben, und eine Kennung wie
  „SN-99887766“ ist kein Ortsname; beides wird jetzt berücksichtigt. Über
  den ganzen Messkorpus fielen die Fehlalarme dadurch von 178 auf 73, ohne
  dass eine einzige Angabe weniger gefunden wurde. Auf durchgehend klein
  geschriebenen Seiten – schlechte Texterkennung – bleibt die Regel außen
  vor, damit dort keine Namen verloren gehen.
- **In Formularen in Großbuchstaben blieben Anschrift und Ort stehen**:
  „LERCHENFELDER STRASSE 42, 1080 WIEN“ wurde nicht als Anschrift
  erkannt – die Muster verlangten Kleinbuchstaben. Aufgefallen ist das
  erst, als ein danebenliegender Fehlalarm wegfiel, der die Zeile bis
  dahin zufällig mitgenommen hatte.
- **E-Mail-Adressen mit firmeninterner Endung blieben stehen**:
  `p.kern@firma.local` wurde nicht als Adresse erkannt – geprüft wurde die
  Endung gegen eine Liste bekannter Domänen, und `.local` steht dort
  nicht. Übrig blieb ein verstümmelter Rest, weil stattdessen ein
  Bruchstück als Webadresse geschwärzt wurde („p.ke"). Betroffen war die
  in Firmennetzen häufigste Domäne überhaupt sowie `.test`, `.example`
  und `.invalid`, die für Beispiel- und Prüfunterlagen reserviert sind.
  Jetzt entscheidet die Form, nicht ein Verzeichnis – und der Platzhalter
  heißt wieder „[EMAIL_1]" statt „[URL_1]".
- **In Formularen in Großbuchstaben blieb das Geburtsdatum stehen**:
  „GEBURTSDATUM: 14.03.1988“ wurde nicht erkannt, „Geburtsdatum:
  14.03.1988“ dagegen schon – die Feldwörter waren
  schreibungsempfindlich. Betroffen war ausgerechnet, was in Formularen,
  Stempeln und Registern am sichersten steht; dasselbe galt für
  „PERSONALNR.“.
- **Lagerplätze galten als Postleitzahl**: „Lagerplatz 3390 Regal C“
  ergab die Ortsangabe „3390 Regal“. In Lagerlisten und Bauplänen steht
  das in jeder Zeile. Betriebsinterne Platzangaben gelten jetzt auch vor
  einer Zahl nicht als Anschrift – dieselbe Regel wie bei „Lagerplatz 12“.
- **Ersatzteil- und Lagerlisten wurden unbrauchbar geschwärzt**:
  Artikel-, Material-, Zeichnungs- und Seriennummern bezeichnen eine Ware
  und keinen Menschen – trotzdem verschwanden sie. „Artikelnummer:
  A-2026-1234 Menge 12“ ergab obendrein den „Ort“ „1234 Menge“, und
  „Lagerplatz 3390“ galt als Anschrift. Eine Postleitzahl steht jetzt für
  sich, und betriebsinterne Platzangaben sind keine Adresse – „Marktplatz
  3“ bleibt selbstverständlich eine.
- **Feldnamen wurden zu Namen**: In Formularen und Stammblättern wurden
  die Beschriftungen selbst geschwärzt – „IBAN“, „PESEL“,
  „Organisasjonsnummer“, „Materialnummer“. Übrig blieb ein Dokument, dem
  man nicht mehr ansieht, was in welchem Feld stand.
- **Platzhalter liefen in den Nachbartext hinein**: In Formularen mit
  dicht besetzten Zeilen überdeckte ein Platzhalter das nächste Feld –
  „Kunde: [NAME_3] [NAMEP[NAME_6]". Zwei Ursachen: Die Einpassung hielt
  den Platz der *nächsten* Fundstelle für frei (dort steht danach aber
  deren eigener Platzhalter), und sie rechnete mit der mittleren
  Zeichenbreite eines Fließtexts. Ein Platzhalter ist durchweg groß
  geschrieben und damit rund ein Sechstel breiter; jetzt wird die Breite
  Zeichen für Zeichen gerechnet statt geschätzt.
- **Statt eines lesbaren Platzhalters erschien ein schwarzer Balken**: Wo
  es eng wurde, fiel der Platzhalter unter eine feste Mindestgröße und
  wurde geschwärzt – ein „[KFZ_KENNZEICHEN_1]" verfehlte sie um drei
  Hundertstel Punkt. Ein Balken sagt nur, *dass* etwas entfernt wurde;
  der Platzhalter sagt **was**. Er ist jetzt bis 4 Punkt zulässig, und
  der Balken bleibt die letzte Zuflucht.
- **Eine Feldbeschriftung konnte am Namen kleben bleiben**: Aus „Kunde:
  Kern, Paul Ansprechpartner ist …" wurde „Paul Ansprechpartner" als
  *ein* Name geschwärzt. Jetzt wird die Beschriftung abgeschnitten – und
  nicht der ganze Treffer verworfen, denn dann wäre „Paul"
  stehengeblieben.
- **Postleitzahlen bei Orten wie „St. Pölten" blieben stehen**: Ortsnamen
  mit abgekürzter Vorsilbe („St. Pölten", „Bad Ischl") wurden gar nicht
  als Ortsangabe erkannt – die Postleitzahl davor blieb im Ergebnis
  stehen. Umgekehrt verschluckte dieselbe Regel bis zu zwei Wörter des
  **nächsten Satzes**: Aus „3913 Linz Bitte senden Sie …" wurde auch das
  „Bitte" geschwärzt. Beides betraf die vier- wie die fünfstellige
  Postleitzahl.

---

## 0.10.15 – 10. August 2026

### Behoben

- **Aus geschwärzten Angaben blieben einzelne Zeichen im Dokument
  stehen**: Aus einer Durchwahl „DW 3100“ blieb eine „3“, aus einem
  Geburtsdatum ein „30.1“. Die Nachprüfung schlug keinen Alarm, weil sie
  nur fragt, ob der *ganze* Wert noch dasteht. Ursache war eine um eins
  verschobene Zuordnung im Inneren: Bei Dokumenten, die jeden Buchstaben
  einzeln setzen – Mitarbeiterverzeichnisse, Tabellen, viele
  Listendrucke –, wurde jedes fünfte Zeichen dem falschen Befehl
  zugeschrieben. An einem echten Verzeichnis mit acht Seiten gemessen:
  vorher blieb ein Bruchstück stehen und eine Seite musste in ein Bild
  umgewandelt werden, jetzt bleibt nichts stehen und keine Seite wird
  umgewandelt – der Text bleibt überall durchsuchbar.
- **Ein Name konnte eine Durchwahl mitverschlucken**: In Verzeichnissen
  las die Erkennung „Tobias · Techniker · DW 2102 · MONTEURE“ als *einen*
  Namen. Entfernt wurde alles, aber die Durchwahl bekam keine eigene
  Nummer – derselbe Vorname trug dadurch an anderer Stelle einen anderen
  Platzhalter. Solche Treffer werden jetzt an der Durchwahl getrennt, und
  jede Angabe bekommt wieder ihre eigene, wiedererkennbare Nummer. An
  einem echten Verzeichnis: 178 → 190 eigenständig erfasste Durchwahlen,
  keine einzige Angabe geht dabei verloren.
- **In klein gesetzten Dokumenten verschwanden die Angaben spurlos**:
  Wo ein „[NAME_1]“ stehen sollte, blieb die Zeile einfach leer – ohne
  Platzhalter und ohne Balken. Betroffen war alles, was kleiner als rund
  6 Punkt gesetzt ist: Mitarbeiterverzeichnisse, Preislisten,
  Tabellenanhänge. Entfernt waren die Angaben, aber niemand konnte sehen,
  *dass* dort etwas entfernt wurde. An einem echten Verzeichnis
  gemessen: vorher trugen 163 von 1015 Fundstellen ihren Platzhalter,
  jetzt alle 1015. Ob eine Zeile zu klein für einen Platzhalter ist,
  entscheidet jetzt der Vergleich mit der übrigen Seite und nicht mehr
  ein fester Wert – ein Platzhalter ist so groß wie der Text, den er
  ersetzt.
- **Von Hand schwärzen wirkte auf gedrehten Seiten nicht**: Manche PDFs
  liegen im Inneren quer und werden erst beim Anzeigen aufgerichtet – bei
  Scans ist das der Normalfall. Auf solchen Seiten meldete das
  Nachbessern „Bereich geschwärzt“ und zeichnete einen Balken, **der Text
  blieb aber in der Datei**. An einem Dienstvertrag gemessen: Von drei
  von Hand geschwärzten Begriffen verschwand keiner; einer traf sogar
  eine andere Stelle im Dokument. Die automatische Bereinigung war davon
  nicht betroffen.
- **Gescannte Seiten wurden geleert**: Ein Scan besteht aus einem Bild
  und unsichtbarem Text aus der Texterkennung. Die Bild-Automatik hielt
  das Bild deshalb für Hintergrundgestaltung und entfernte es – übrig
  blieb ein leeres Blatt. Dazu wird bei einem Scan jetzt auch **im Bild**
  geschwärzt: Was man liest, steht dort und nicht im Text.
- **Auf gedrehten Seiten fehlten alle Platzhalter**: Statt „[NAME_1]“
  erschien überall ein schwarzer Balken, und „Zurücknehmen“ meldete, der
  Platzhalter sei nicht zu finden. Er stand tatsächlich nirgends im
  Dokument. Platzhalter überstehen jetzt auch das Rastern einer Seite.
- **Die Seitenansicht hatte keinen Knopf, den man erkennt**: Das
  Werkzeug für „Word als Word“ stand ohne Bild in der Leiste.
- **Die Seitenansicht war doppelt so langsam wie nötig**: Vor jedem
  Rendern richtete sich LibreOffice neu ein. Nach dem ersten Mal
  halbiert sich die Wartezeit beim Ersetzen (6,6 auf 3,0 Sekunden
  gemessen).
- **Das neue Symbol im Infobereich gab es nur unter Windows**: Menüleiste
  am Mac und Infobereich unter Linux bekamen weiter die alte, matschige
  Fassung. Unter Linux war es obendrein ein schwarzer Klotz, der auf
  dunkler Leiste kaum zu sehen war.

---

## 0.10.14 – 10. August 2026

### Neu

- **Von Hand schwärzen, ohne vorher zu bereinigen**: Über „Datei → Von
  Hand schwärzen …“ lässt sich jede unterstützte Datei direkt im
  Nachbessern-Fenster öffnen und von Hand schwärzen – ohne dass eine
  Erkennung läuft. Das Original bleibt wie immer unangetastet; gearbeitet
  wird an einer Kopie.

- **Die Seitenansicht bringt LibreOffice selbst mit**: Fehlt es auf dem
  Rechner, bietet der Knopf es beim ersten Klick zum Laden an (einmalig
  ca. 276 MB). Es wird nur zum Anzeigen gebraucht – bereinigt wird wie
  bisher.

- **Word-Dokumente als Word ansehen und nachbessern**: Im
  Nachbessern-Fenster gibt es für Word-, Excel-, PowerPoint- und
  LibreOffice-Dateien jetzt eine **Seitenansicht** – das Dokument so, wie
  es aussieht, statt einer Textliste. Ein Rahmen um eine Stelle ersetzt sie
  **im Dokument selbst**: Word bleibt Word, das Ergebnis ist keine Bilddatei
  und kein PDF. Der Wert wird dabei überall im Dokument ersetzt, nicht nur
  an der markierten Stelle – bei personenbezogenen Daten ist das fast immer
  gewollt, und die Statuszeile sagt es.

  Excel-Dateien erscheinen dabei als **Tabelle** – mit Zeilen, Spalten und
  Formaten statt einer Kolonne aus Zellinhalten; PowerPoint als Folien.
  Unterstützt sind Word, Excel, PowerPoint und die LibreOffice-Formate.

  Dafür wird LibreOffice gebraucht; ist keines da, bleibt es bei der
  Textansicht und der Knopf erklärt warum.

- **„Öffnen …“ im Nachbessern-Fenster**: Das Ergebnis mit dem Programm
  öffnen, das der eigene Rechner dafür vorsieht – Word öffnet Word, ein PDF
  den PDF-Betrachter, ein Bild die Bildanzeige. Kennt das System für die
  Dateiart nichts, wird das gesagt statt eines Knopfes, der scheinbar
  nichts tut.

---

## 0.10.13 – 10. August 2026

### Neu

- **Diese Liste ist im Programm lesbar**: Unter „Hilfe & FAQ“ steht sie
  jetzt als eigene Themen – und ist damit über das Suchfeld auffindbar. Wer
  wissen will, was sich geändert hat, muss dafür nicht die Website
  aufsuchen.
- **Neuerungen vor dem Aktualisieren**: Bietet das Programm eine neue
  Fassung an, zeigt der Knopf „Neuerungen“ deren Änderungen direkt im
  Fenster statt den Browser zu öffnen.
- **„Ohne maximale Erkennung starten“**: Kündigt das Programm vor einem
  umfangreichen Lauf eine lange Wartezeit an und liegt das an der
  KI-Stufe, lässt sich derselbe Lauf mit einem Klick ohne sie starten. Die
  Einstellung bleibt davon unberührt – es gilt nur für diesen Lauf.

### Behoben

- **Das Symbol im Infobereich war matschig**: Alle Größen entstanden durch
  Herunterrechnen aus einem 256-Bildpunkt-Bild. Jetzt wird jede Größe
  einzeln aus der Zeichnung gerastert, und für 16 bis 24 Bildpunkte gibt es
  eine eigene, kräftigere Fassung – dort verschmolzen die beiden
  Schwärzungsbalken sonst zu einem grauen Klotz. Das Mac-Symbol entsteht
  auf demselben Weg statt nachträglich verkleinert zu werden.
- **Abbrechen sagt nicht mehr „der laufende Schritt wird beendet“**: Das
  stimmte, solange ein KI-Abschnitt nicht unterbrechbar war – jetzt hört
  der Lauf sofort auf.

---

## 0.10.12 – 10. August 2026

### Neu

- **Globale Tastenkürzel unter Windows**: `Strg+Umschalt+V` schaltet die
  Überwachung der Zwischenablage, `Strg+Umschalt+C` bereinigt einmalig.
  Beide lassen sich im Programm-Reiter ändern. Auf dem Mac gab es sie
  schon, unter Windows bisher nicht.
- **Hilfe und FAQ sind durchsuchbar**: Ein Suchfeld über der Themenliste
  sucht in **allen** Themen samt Inhalt – wer eine Antwort sucht, weiß
  selten, unter welcher Überschrift sie steht. Die Fundstellen sind im Text
  markiert, F3 springt weiter.
- **Grafikbeschleunigung für die maximale Erkennung**: Wird beim
  Einschalten der KI-Stufe angeboten und nachgeladen. Ob sie genutzt wird,
  entscheidet eine Messung auf dem eigenen Rechner – eine schwache
  eingebaute Grafik kann langsamer sein als der Prozessor, und das lässt
  sich nicht vorhersagen. Ein Paket bedient NVIDIA, AMD und Intel.

### Behoben

- **Digitale Signaturen wurden als Text gelesen**: Ein signiertes PDF
  brachte die Erkennung dazu, den kryptografischen Block zu durchsuchen –
  aus Binärrauschen wurden Dutzende Platzhalter, die Bereinigung dauerte
  minutenlang, und das Signaturfeld wurde beim Schreiben beschädigt. Ein
  Ausgabeprotokoll ging damit von 78 unsinnigen Ersetzungen auf zwei
  richtige, die Dauer von Minuten auf drei Sekunden.
- **Signaturen werden jetzt entfernt**: Sie sind nach jeder Bereinigung
  ohnehin ungültig, tragen aber Name und Mailadresse der unterzeichnenden
  Person im Zertifikat. Das Ergebnis sagt es ausdrücklich; das Original
  bleibt unverändert signiert.
- **Zeilenenden blieben nicht, wie sie waren**: Bereinigte Text-, Markdown-
  und CSV-Dateien bekamen unter Windows vor jeder Zeile einen zusätzlichen
  Wagenrücklauf, Unix-Dateien ungefragt Windows-Zeilenenden, und die
  Byte-Reihenfolgemarke ging verloren – ohne sie öffnet Excel eine
  UTF-8-CSV falsch.
- **Tabulatoren gingen in Word-Dateien verloren**: In Lebensläufen,
  Tabellen und Formularen bauen Tabstopps die Spalten. Ohne sie klebten
  „Seit 08.2010“ und der Firmenname aneinander – und daraus wurde prompt
  eine Telefonnummer.
- **Ein deutsches Dokument galt als Rumänisch**: Seriennummern zerfallen in
  Bruchstücke wie „d“, „g“ und „gb“, und die sind in manchen Sprachen
  Funktionswörter. Bei kurzen, sachlichen Dokumenten entschied dieser
  Schutt die Sprachwahl – samt Angebot, ein 482 MB großes Modell zu laden.
  Einzelne Buchstaben zählen nicht mehr als Beleg, und nach einem Modell
  wird erst gefragt, wenn die fremde Sprache deutlich besser passt.
- **Datum im Dateinamen galt als Telefonnummer**: Aus
  „05082026_bericht.pdf“ wurde „[TELEFON_1]_bericht_bereinigt.pdf“.
- **Überschriften und Anweisungen galten als Namen**: „Ausgabeprotokoll“
  wurde geschwärzt, ebenso „Lösche dazu diese Seite“ in einer Vorlage. Ein
  Name hinter dem Wort bleibt unangetastet – „Vertrag Müller“ behält
  seinen Namen, und „Herr Lösche“ mitten im Satz auch.
- **Die Word-Textansicht zeigte alles mehrfach**: Ein Textrahmen steht im
  Dateiformat zweimal – einmal modern, einmal als Altfassung für ältere
  Word-Versionen. Zum Bereinigen ist das richtig, zum Ansehen war es eine
  Doppelung. Dazu bleiben Leerzeilen erhalten, damit der Text wieder
  Abschnitte hat.
- **Die Zeitschätzung kannte die eingeschalteten Stufen nicht**: Ein
  Dokument mit 153 Bildern stand mit „etwa 90 Sekunden“ da und brauchte mit
  maximaler Erkennung über eine halbe Stunde. Jetzt zählen die Stufen mit,
  der Hinweis nennt die richtige Ursache, und nach der Messung auf dem
  eigenen Rechner stimmt die Zahl auch.
- **Abbrechen wirkt sofort**: Während der KI-Prüfung wurde erst zwischen
  zwei Abschnitten gefragt – ein Abbruch konnte dadurch eine Stunde
  brauchen. Jetzt greift er mitten in der Antwort.

### Geändert

- **Die Zusatzmodelle heißen nach ihrem Nutzen**: „Erweiterte Erkennung“
  und „Maximale Erkennung (KI)“ statt technischer Bezeichnungen, mit einer
  ehrlichen Angabe der Kosten. Am KI-Haken stand „kostet wenige Sekunden je
  Dokument“ – das war falsch.
- **Seitenblättern und Zoom sitzen im Nachbessern-Editor unten**, wie in
  Acrobat, Word und LibreOffice.
- **Nebentexte im Dunkelmodus sind heller**: Sie erfüllten die Norm und
  waren trotzdem schwer zu lesen.

---

## 0.10.11 und früher – 7. bis 9. August 2026

### Verbessert

- **Acht Sprachen statt fünf im Messstand**: Französisch, Italienisch und
  Portugiesisch sind dazugekommen – mit ihren Feldwörtern für Geburtsdatum,
  Personalnummer und Formularbeschriftungen.
- **Anredeformeln und gewöhnliche Wörter sind keine Namen**: „Gentile“,
  „Cordiali“, „Bene“, „Obrigado“ – manche Sprachmodelle halten am
  Satzanfang stehende Alltagswörter für Personen. Echte Namen sind davon
  nicht betroffen; sie stehen in keiner Stoppwortliste.

- **Ausgefüllte Formulare**: In einem Formular steht der Wert allein in
  seinem Kästchen, und was er bedeutet, sagt die Beschriftung darüber. Sie
  wird jetzt mitgelesen – „Familienname“, „Apellidos“, „Achternaam“,
  „Efternamn“, „Nom de famille“, „Cognome“, „Apelido“, dazu „Geburtsort“
  und „Anschrift“ und ihre Entsprechungen in acht Sprachen. Ein ganzer Satz unter einer Beschriftung bleibt unangetastet:
  Das ist eine Erläuterung, kein Feldwert.
- **Britische Umsatzsteuernummer** („GB123456789“) wird erkannt.

- **Personalnummern werden erkannt** – „Personalnr.: P-40711“,
  „Staff no.“, „N.º personal“, „Personeelsnr.“, „Anställningsnummer“. Die
  nackte Kennung bleibt unangetastet: Erst die Beschriftung davor macht sie
  zur Kennung eines Menschen, eine Bestell- oder Artikelnummer also nicht.
  Für hauseigene Formen ohne Feldwort bleiben die firmenweiten
  Begriffslisten zuständig.
- **Durchwahlen auch auf Englisch**: „extension 417“ blieb stehen, weil das
  Muster nur „Ext.“ groß geschrieben kannte. Ebenso neu: „Nebenstelle“,
  „doorkiesnummer“, „anknytning“, „extensión“.

- **Namen in Verzeichnissen und Rastern werden jetzt gefunden.** In einer
  Mitarbeiterliste steht jeder Name allein in einer kurzen Zeile, zwischen
  den Einträgen liegt eine Leerzeile – für das Sprachmodell ist damit jedes
  Wort ein einsamer Satzanfang und kein Name. Solche Aufstellungen werden
  jetzt zusätzlich als Aufzählung gelesen – in zwei Formen, weil sie
  verschiedene Namen treffen. Dazu kommt die **Bauform des Verzeichnisses**:
  Steht in derselben Zeile bei den meisten Einträgen ein erkannter Name,
  steht dort auch bei den übrigen einer – so fallen auch Namen, die das
  Sprachmodell nicht kennt.

  Über den Messkorpus stieg die Fundquote damit auf **100 %** in allen fünf
  Sprachen mit eigenem Sprachmodell (Deutsch, Englisch, Spanisch,
  Niederländisch, Schwedisch), bei unverändert **null Fehlalarmen**. Zuvor
  waren es 92 %. Lieferanten-, Städte- und Warenlisten derselben Bauform
  bleiben unangetastet.

- **Britische und amerikanische Anschriften werden erkannt.** „221B Baker
  Street“ fand das Sprachmodell, „1 High Street“ nicht – es kennt berühmte
  Straßen und rät bei den übrigen. Ein Muster für Hausnummer plus Straßentyp
  (Street, Road, Avenue, Lane, Way …) schließt die Lücke; dazu kommt der Ort
  mit Postleitzahl („London EC1A 1BB“, „Springfield, IL 62704“). Beides gilt
  für die Länderauswahl „Vereinigtes Königreich“ und „Vereinigte Staaten“.
  Ein Leerzeichen, das die Texterkennung in die Postleitzahl streut, stört
  nicht mehr – genau daran scheiterte der Briefkopf bisher.

### Behoben

- **Das Programm führte kein Protokoll**: Warnungen gingen im fertigen
  Programm ersatzlos verloren, weil ein Fenster-Programm keine Konsole hat.
  Sie stehen jetzt in `protokoll.log` neben den Einstellungen – mitwachsend
  begrenzt, damit sie die Platte nicht füllen. Läuft alles normal, bleibt die
  Datei **leer**; wer einen Fehler meldet, kann sie mitschicken.
- **Das Mac-Ablegebild hatte kein eigenes Symbol** – im Finder erschien der
  graue Standard-Datenträger statt des Programmsymbols.

- **Geburtsdaten nur auf Deutsch und Englisch erkannt**: „Fecha de
  nacimiento“, „Geboortedatum“ und „Födelsedatum“ blieben stehen – der
  Erkenner war an die deutschen Muster gekoppelt und deshalb nur für zwei
  Sprachen geladen. Ein Geburtsdatum ist aber in jeder Sprache eines. Auch
  die Schreibweisen mit Bindestrich (14-03-1988) und mit dem Jahr voran
  (1988-03-14) werden jetzt gelesen.

- **Geburtsdaten in Tabellen blieben stehen**: In einer Personaltabelle
  enthält die Zelle nur „14.03.1988“ – was das ist, sagt allein die
  Spaltenüberschrift. Die wird jetzt mitgelesen, ohne dass sich am Dokument
  etwas ändert; die Überschrift selbst bleibt unangetastet.
- **Zwei Tabellenzellen konnten verschmelzen**: Sporadisch wurden zwei
  völlig verschiedene Zellen als ein Textblock behandelt – eine Ersetzung
  konnte dadurch in der falschen Zelle landen.

- **Datumsangaben und Uhrzeiten wurden geschwärzt**: „02.04.2026“
  verschwand aus Formularen und Tabellen und trug den Platzhalter
  „[TELEFON]“ – die Ziffernfolge liest sich als Rufnummer mit Vorwahl.
  Dasselbe galt für „02-04-2026“, „2026-04-02“ und die Uhrzeit „09:12“ aus
  einem Chatverlauf. Im Fließtext fiel es nie auf, weil dort ein Punkt
  folgt; im Formularfeld und in der Tabellenzelle steht keiner.
- **Feldbeschriftungen wurden geschwärzt**: „Personalnr.“, „E-Mail“,
  „UID-Nummer“, „Standort“, „Ciudad“, „Adress“ galten als Personennamen oder
  Orte – allein in ihrer Zeile stehend rät das Sprachmodell. In Tabellen
  kostete das die Spaltenüberschriften. Erkannt werden Beschriftungen jetzt
  auf Deutsch, Englisch, Spanisch, Niederländisch und Schwedisch.

- **Harmlose Dateinamen wurden umbenannt**: Aus „altbrief.htm“ wurde
  „[ORT_1]_bereinigt.htm“. Ein Dateiname ist kein Satz – ohne Nachbarwörter
  riet die Namenserkennung. Im Dateinamen zählen jetzt nur noch Angaben, die
  sich selbst prüfen (E-Mail, IBAN, Telefon, Steuernummer) sowie
  Personennamen aus mindestens zwei großgeschriebenen Teilen;
  „Lebenslauf_Anna_Musterfrau“ wird also weiterhin bereinigt, „auto.pdf“
  bleibt „auto.pdf“.
- **Bereinigen war unnötig langsam**: Das Programm fragte bei jedem Absatz
  neu beim Dateisystem nach, welche Sprachmodelle installiert sind – bei
  einem Dokument mit 120 Absätzen kamen 140.000 Abfragen zusammen. Es merkt
  sich die Antwort jetzt und bemerkt trotzdem, wenn eine Sprache dazukommt.
  Bereinigen ist dadurch rund **ein Drittel schneller**.

- **IBANs wurden meistens übersehen**: Stand hinter der Kontonummer ein Wort
  mit vier oder mehr Zeichen – „… 3457 3201 **wird** belastet“ –, fand die
  Erkennung sie nicht. In Briefen ist das der Regelfall. Ein eigener
  Erkenner rechnet jetzt Länge und Prüfsumme nach; was daneben steht, ist
  gleichgültig. Auch eine über zwei Zeilen gerissene IBAN wird gefunden.
- **Ein zweiter Lauf beschädigte bereits bereinigte Dateien**: Platzhalter
  des ersten Laufs wurden selbst für Namen und Orte gehalten – aus
  „[NAME_1]“ wurde „[[ORT_1]]“, und die Bedeutungen vertauschten sich.
  Platzhalter bleiben jetzt unangetastet.
- **Namen in der Anrede**: „Herr von der Heide", „Frau O'Brien" und „Herr
  Berlin" blieben stehen – Adelsprädikate, Apostrophe und Namen, die zugleich
  Orte sind, weichen von dem ab, was das Sprachmodell gelernt hat. Nach einer
  Anrede steht jetzt zuverlässig ein Name; Titel und Funktionen („Sehr geehrte
  Frau Bundesministerin") bleiben ausgenommen.
- **Kreditkartennummern wurden gar nicht erkannt**: Der mitgelieferte
  Erkenner war nie geladen worden – obwohl Handbuch und FAQ die Kreditkarte
  ausdrücklich nennen. Jetzt wird sie samt Prüfziffer gefunden, mit und ohne
  Leerzeichen.
- **Neu erkannt**: BIC/SWIFT einer Bankverbindung, Fahrgestellnummer (FIN),
  IMEI eines Mobilgeräts und MAC-Adresse eines Rechners. Alle vier stehen
  regelmäßig in Geschäftsunterlagen und zeigen auf eine Person oder ihr Gerät.
- **Namen in Dateinamen**: Aus `Lebenslauf_Anna_Musterfrau.pdf` wird
  `Lebenslauf_[NAME_1]_bereinigt.pdf` – mit derselben Nummer wie im Dokument.
  Der beschreibende Teil bleibt stehen, damit die Datei auffindbar bleibt; das
  Original behält seinen Namen. Auch Anhangnamen in E-Mails werden bereinigt.
  Zuvor blieb der Name stehen, weil Unterstriche ihn für die Erkennung zu
  einem einzigen Wort machten.
- **HTML: Bildbeschreibungen, Seitenkopf und Kommentare**: Der
  Alternativtext eines Bildes, die Angaben `author` und `description` im
  Seitenkopf und interne HTML-Kommentare blieben stehen. Technische Angaben
  wie `viewport` bleiben unangetastet.
- **Fotos gaben Fotograf und Aufnahmeort preis**: In den EXIF-Daten eines
  Bildes stehen unsichtbar der Name des Fotografen, die Copyright-Zeile und
  oft die GPS-Koordinaten des Aufnahmeorts. Sie blieben stehen – im
  einzelnen Bild wie im eingebetteten. Jetzt werden sie entfernt; nur die
  Ausrichtung bleibt, sonst läge ein Hochformat plötzlich quer.
- **Excel und PowerPoint: Kopfzeile, Kommentar-Verfasser und Bildbeschreibung**:
  „Bearbeitet von …“ in der Kopfzeile, der Name hinter einem Zellkommentar und
  der Alternativtext eines Bildes („Foto von …“) blieben stehen – sie liegen
  außerhalb der eigentlichen Textfelder. Blattnamen bleiben weiterhin
  unangetastet, weil Formeln über den Namen auf das Blatt verweisen; stehen
  dort personenbezogene Daten, wird das jetzt ausdrücklich gemeldet.
- **Ausgefüllte PDF-Formulare blieben lesbar**: Der Wert eines Formularfelds
  steht nicht im Seitentext, sondern am Feld – ebenso der Text einer Notiz
  samt Verfassernamen und die Beschriftung eines Lesezeichens. Alle drei
  blieben stehen und waren für jeden auslesbar. Jetzt werden sie mit
  denselben Platzhaltern ersetzt wie der Seiteninhalt.
- **Firma und Vorgesetzter blieben in Word-Dateien stehen**: Beide stehen
  nicht in den gewöhnlichen Dokumenteigenschaften, sondern in einem eigenen
  Eigenschaftenblatt. Excel und PowerPoint räumten dort längst auf, Word
  nicht – obwohl das Handbuch die Firma ausdrücklich nennt.
- **Italiens Codice fiscale wurde nie gefunden**: Der wichtigste
  italienische Personenkennzeichen – er enthält Name, Geburtsdatum,
  Geschlecht und Geburtsort – wurde zu schwach bewertet und fiel immer
  unter die Erkennungsschwelle. Jetzt wird er über Form und Prüfzeichen
  sicher erkannt.
- **Dänische und norwegische Telefonnummern in Landesschreibweise**: Beide
  Länder haben keine Amtskennziffer; „33 66 33 66“ ist dort eine
  vollständige Nummer und wurde übersehen. Thailand, Südafrika, Nigeria und
  die Philippinen waren ebenso betroffen.
- **Gesperrt geschriebene Namen blieben stehen**: „A n n a   H u b e r“ auf
  Briefköpfen und Urkunden erkennt das Programm jetzt als Namen.

- **Je-Rechner-Installation konnte nichts nachladen**: Unter
  `C:\Program Files` installiert, scheiterten Sprachpakete und Modelle mit
  „Permission denied" - nachladbare Daten liegen jetzt unter LocalAppData,
  wie auf dem Mac im Application Support.
- **Nachgeladene OCR-Sprache verdeckte die mitgelieferten**: Nach dem ersten
  Sprach-Download „fehlte" plötzlich Englisch - der neue Sprachdaten-Ordner
  übernimmt jetzt auch, was die mitgelieferte Maschine dabeihat (eng, osd).

- **Installer wartete auf ein offenes Programmfenster**: Der Schalter
  `--registrieren`, mit dem das Setup das Kontextmenü einträgt, startete die
  volle Oberfläche statt still zu arbeiten - das Setup stand dann bei
  „Kontextmenü wird eingetragen …", bis jemand das Fenster schloss. Beide
  Setup-Schalter (`--registrieren`, `--abmelden`) laufen jetzt ohne Fenster.

- **Texterkennung liegt jedem Paket bei** (Deutsch, Englisch): Bisher las
  ein Rechner ohne eigene Tesseract-Installation gar keine Bilder - die
  Sprachdateien fehlten im Paket. Ebenso behoben: Nach dem Verwalten der
  Sprachen zeigte die Statuszeile bis zum Neustart den alten Stand.
- **Je-Rechner-Installationen übernehmen vorhandene Modelle**: Was früher mit
  Verwalterrechten nach Program Files geladen wurde, wird in die neue Ablage
  kopiert statt neu heruntergeladen.

### Neu

- **Geburtsdaten fallen immer**: „Geburtsdatum: …", „geboren am …", „geb. …",
  „* 12.05.1985" sowie „Date of Birth"/„born on" werden als eigene Angabe
  entfernt - unabhängig von der Einstellung „Datumsangaben ebenfalls
  entfernen". Gewöhnliche Liefer- und Rechnungsdaten bleiben stehen.
- **Der erste Start bietet die beste Erkennung gesammelt an**: Hoch-Stufe und
  Gesichter-Stufe in einem Dialog; die KI-Stufe wird bei genug
  Arbeitsspeicher im Protokoll empfohlen.
- **Zwölf Oberflächensprachen**: Neben Deutsch und Englisch jetzt
  Französisch, Spanisch, Italienisch, Niederländisch, Polnisch,
  Portugiesisch, Schwedisch, Dänisch, Norwegisch und Finnisch – jeweils
  vollständig, samt Handbuch, FAQ, Datenschutzhinweis und Lizenzhinweisen.
  Umstellbar unter „Mehr Einstellungen → Sprache der Oberfläche".
- **Frankreich, Dänemark und Norwegen bei der Erkennung**: Französische
  Sozialversicherungsnummer und SIREN/SIRET, dänische CPR- und CVR-Nummer,
  norwegische Geburts- und Organisationsnummer – jeweils mit
  Prüfziffernrechnung, damit nicht jede Zahlenkette ein Treffer wird.
- **Menüzeile im Fenster**: Datei, Programm und Hilfe führen dieselben Wege
  wie die Knöpfe. Auf dem Mac erscheint sie oben am Bildschirm, in der
  eingestellten Sprache – vorher stand dort eine englische Standardzeile.
- **Begriffslisten für ganze Häuser**: Eine Datei `firmen_regeln.json`, von
  der Verwaltung zentral gepflegt, gilt zusätzlich zu den persönlichen
  Regeln. Im Regelfenster steht sie unter „Von der Verwaltung" zum
  Nachsehen. Liegt sie auf einem Netzlaufwerk, hält das Programm eine
  örtliche Kopie – ohne Netz gelten die Regeln weiter.

### Geändert

- **Schneller bereinigt**: Die Suche nach Namen in Großbuchstaben lief bisher
  über den gesamten Text – ein zweites Mal, zusätzlich zur normalen Prüfung,
  und damit doppelt so lange. Jetzt sieht sie nur noch die Zeilen, in denen
  überhaupt Großbuchstaben stehen. Die Erkennung wird dadurch spürbar
  schneller, ohne dass ein Name verlorengeht.

- **Das Programm heißt jetzt Maskuro** (vorher „PII Cleaner"). Der Name kommt
  von „Maske/maskieren" – die schwarzen Balken der Schwärzung sind Masken über
  den personenbezogenen Daten. Für Bestehendes ändert sich nichts:
  Einstellungen und heruntergeladene Modelle ziehen beim ersten Start
  automatisch um, und Aktualisierungen finden ihr Ziel wie bisher. Sichtbar
  sind der neue Name in Fenstern, Menüs und Dateinamen der
  Installationspakete (`Maskuro-…`). Lizenzschlüssel beginnen jetzt mit
  `MASK1.` – die wenigen vor der Umbenennung ausgestellten Testschlüssel
  werden auf Anfrage kostenlos neu ausgestellt.
- **KI-Stufe überall dabei**: Der Baustein `llama-cpp-python` gehört jetzt zu
  jeder Installation – der Haken „Treffer zusätzlich mit lokalem KI-Modell
  prüfen" führt damit direkt zum Modell-Download statt zu einer
  Fehlermeldung.
- **KI-Stufe in Sekunden statt Minuten**: Das KI-Modell arbeitet nur noch als
  Schiedsrichter über Grenzfälle (wenige Sekunden je Dokument). Der
  Zusatz-Finder, der je Absatz über 20 Sekunden brauchte, ist abgeklemmt,
  bis er gebündelt laufen kann. Die Schiedsrichter-Urteile selbst laufen
  gebündelt (acht je Modellaufruf) - auch Namenslisten mit vielen
  Grenzfällen bleiben damit im Sekundenbereich.
- **Namenslisten raten keine Sprache mehr**: Ein Verzeichnis ohne Fließtext
  wurde bisher schon durch einen einzigen zufälligen Worttreffer einer
  fremden Sprache zugeordnet (samt Frage nach einem Sprachpaket). Jetzt
  braucht die Erkennung einen Mindest-Beleg, sonst bleibt es bei Deutsch.
- **Länder und Sprachmodelle richten sich nach dem System**: Wer das
  Programm auf Schwedisch benutzt, startet mit schwedischen Nummern statt
  mit deutschen, und der erste Start schlägt Schwedisch statt Deutsch vor.
  Maßgeblich sind Oberflächensprache und eingestellte Region; eine eigene
  Auswahl bleibt unangetastet.
- **Datenschutz sichtbar im Fenster**: Eine Zeile im Kopf nennt den
  belegbaren Punkt – 100 % örtliche Verarbeitung, ohne Cloud und Konto – und
  führt mit einem Klick zum vollständigen Datenschutzhinweis. Die FAQ
  beantwortet die DSGVO-Frage ausführlich, ohne Konformität zu versprechen,
  die kein Werkzeug geben kann.
- **Platzhalter in PDFs einheitlich**: Eingelegte und überlagerte Platzhalter
  tragen dasselbe gedeckte Rot.

---

## 0.10.0 – 7. August 2026

### Neu

- **Sichtbarer Fortschritt**: Word-, Excel-, PowerPoint- und
  OpenDocument-Dateien melden während der Bereinigung, wo die Arbeit steht
  („Absatz 40 von 120"), und eine kleine Puls-Anzeige zeigt bei langen
  Läufen durchgehend Leben - nichts wirkt mehr eingefroren.
- **KI-Stufe** (zuschaltbar): Ein lokales Sprachmodell prüft grenzwertige
  Treffer und ergänzt eigene Funde – die gründlichste Stufe, dauert deutlich
  länger. Das Modell wird beim Einschalten einmalig geladen (ca. 2,4 GB) und
  arbeitet danach vollständig örtlich. Verhindert auch Über-Schwärzungen:
  Fachbegriffe wie „Baremetal" bleiben stehen.
- **Gesichter unkenntlich machen** (zuschaltbar): Porträts in behaltenen
  Bildern – etwa im Lebenslauf – werden verpixelt. Das kleine Erkennungsmodell
  liegt dem Programm bei.
- **Einmal Gefundenes fällt überall**: Wird „M-Computer HandelsgesmbH"
  erkannt, verschwindet auch das spätere nackte „M-Computer" – ebenso der
  Nachname allein, wenn der volle Name gefunden wurde.
- **Beschäftigungszeiträume** („06/2009 – 04/2025") gelten als Datumsangaben,
  **Schulnamen** („BRG 12") werden erkannt.
- **PDF-Platzhalter stehen im Lesefluss**: Wer die bereinigte PDF kopiert
  oder einer KI gibt, findet „[ORGANISATION_2]" an der Stelle der Fundstelle,
  nicht gesammelt am Seitenende.
- **macOS**: Aktualisierungen installieren sich selbst (einhängen, kopieren,
  auswerfen – mit Neustart-Angebot). Beim Start wird einmalig die beste
  Namenserkennung angeboten. Firmennamen werden ab Werk entfernt. Die
  Zusatzmodelle sind in den Einstellungen gruppiert, die Länderliste ist
  rollbar.

### Behoben

- Nach dem Kopieren ohne Treffer blieb auf dem Mac ein Wartehinweis in der
  Zwischenablage – Einfügen wirkte leer.
- Der Bereinigen-Knopf sah auf dem Mac immer gesperrt aus.
- Der Raster-Rückfall der PDF-Schwärzung zeigte im Seitenbild lesbar, was
  er entfernen sollte; verfehlte Fundstellen werden jetzt übermalt.
- Der Text-Auszug gerasterter Seiten verlor alle Leerzeichen.

## 0.9.7 – 6. August 2026

### Neu

- **PII Cleaner läuft jetzt vollwertig auf dem Mac** (Apple Silicon): als
  App mit klassischem Ablegebild – öffnen, in den Programme-Ordner ziehen,
  fertig. Mit dabei: Symbol in der Menüleiste samt Menü, globale
  Tastenkürzel, „Mit dem System starten" und das Kontextmenü im Finder.
  Schließen legt das Programm in die Menüleiste und räumt das Dock; beendet
  wird über das Menü des Symbols – wie unter Windows.
- **Bilder liest der Mac ohne jede Zusatzinstallation**: Die Texterkennung
  nutzt die systemeigene Erkennung von macOS. Es muss nichts heruntergeladen
  oder beigelegt werden, und die Erkennungsgüte ist in aller Regel besser
  als die der bisherigen schnellen Sprachdateien.
- **Alle Systeme aus einem Guss**: Jede Freigabe entsteht für Windows,
  macOS und Linux gleichzeitig aus demselben Stand; die
  Aktualisierungsprüfung bietet jedem System sein Paket an. Gibt es für das
  eigene System (noch) kein Paket, sagt das Programm das ehrlich, statt
  einen Fehler zu melden.
- **Dunkles Erscheinungsbild**: Unter *Programm → Erscheinungsbild* stehen
  „Wie das System", „Hell" und „Dunkel" zur Wahl. „Wie das System" folgt der
  Vorgabe des Betriebssystems (Windows und macOS); im hellen Modus bleibt
  alles beim vertrauten Aussehen.
- **Text und Bildschirmfotos ohne Datei bereinigen**: Strg+V im Fenster
  öffnet ein Fenster zum Einfügen, Bereinigen und Herauskopieren; ein
  kopiertes Bildschirmfoto öffnet das Bild-Fenster mit Vorschau. Kopierte
  Dateien landen bei Strg+V direkt in der Dateiliste.
- **Der Zwischenablage-Wächter startet nie mehr von selbst**: Auch wenn er
  beim letzten Beenden lief, beginnt jede Sitzung mit ausgeschaltetem
  Wächter – Einschalten ist eine bewusste Handlung (Häkchen, Taskleiste
  oder Tastenkürzel).
- **Der Zwischenablage-Wächter hat zwei Betriebsarten**: *sofort bereinigen*
  (wie bisher – Einfügen liefert die saubere Fassung) oder *erst im Fenster
  melden* – das Original bleibt einfügbar, kopierter Inhalt öffnet sich im
  Bereinigen-Fenster, erst der Klick ersetzt ihn.
- **Zweiter Kontextmenü-Eintrag „Personenbezogene Daten entfernen
  (sofort)"**: startet die Bereinigung ohne weiteren Klick, sobald die
  Sprachmodelle bereit sind. Der bisherige Eintrag öffnet weiterhin das
  Fenster, um Einstellungen und Bilder vorher zu prüfen. Fortschritt,
  Warnungen und die Rückfrage vor großen Läufen bleiben in beiden Fällen
  sichtbar.
- **Webseiten** werden bereinigt (`.html`, `.htm`): gespeicherte Seiten,
  HTML-Rechnungen, exportierte Berichte. Der Text wird in den Knoten ersetzt,
  Layout, Kodierung und Doctype bleiben erhalten; Skripte und Stile bleiben
  unangetastet. `mailto:`- und `tel:`-Verweise werden mitsamt dem sichtbaren
  Linktext ersetzt – auch im HTML-Teil von E-Mails.
- **E-Mail-Dateien** werden bereinigt (`.eml`): Absender, Empfänger und
  Betreff werden ersetzt, die Weg-Kopfzeilen (Received-Kette, Message-IDs,
  X-Kopfzeilen mit Rechnernamen und IP-Adressen) vollständig entfernt.
  Anhänge in unterstützten Formaten werden mitbereinigt und behalten
  dieselben Platzhalter-Nummern wie der Mailtext; auch Dateinamen werden
  bereinigt. Ungeprüfte Anhänge werden ausdrücklich genannt.
- **Der erste Start erklärt sich selbst:** Die Sprache des Betriebssystems
  wird automatisch eingerichtet, statt mit dem Sprachfenster zu beginnen.
  Ohne Netzverbindung fragt das Programm wie bisher.
- **Bereinigte Dateien öffnen sich auf Wunsch von selbst** in der
  Standardanwendung (abschaltbar; bei Stapelläufen höchstens drei Fenster).
- **Die Installation meldet ihre Fertigstellung** mit einem Abschlussfenster
  und dem Häkchen „PII Cleaner jetzt starten".
- **Der Aktualisierungskanal ist wählbar** (Stabil / Vorschau /
  Testfassung) – für alle, die Vorabfassungen ausprobieren wollen.
  Installiert wird weiterhin nur vorwärts, nie eine ältere Fassung.
- **Excel- und PowerPoint-Dateien** werden bereinigt (`.xlsx`, `.xlsm`,
  `.pptx`) – Zellinhalte, Folientexte, eingebettete Bilder und die
  Dateieigenschaften mit Verfasser und Bearbeiter.
- **Bilddateien** können unmittelbar bereinigt werden (`.png`, `.jpg`, `.bmp`,
  `.tif`, `.webp`). Anschriften und Namen darin werden geschwärzt.
- **Text in Bildern wird jetzt in allen Dokumentarten geprüft.** Bisher
  geschah das nur in PDF-Dateien; ein Briefkopf, der als Bild in einem Word-
  oder OpenOffice-Dokument lag, blieb unangetastet. Das ist behoben.
- **Fehlt die Sprache eines Dokuments, wird sie erkannt und kann nachgeladen
  werden.** Bisher wurde in einem solchen Fall stillschweigend mit einer
  anderen Sprache gearbeitet – das Ergebnis sah aus wie ein richtiges, obwohl
  Namen fehlten und harmlose Wendungen geschwärzt waren.

### Verbessert

- **Die Sprachverwaltung zeigt beim Laden echten Fortschritt**: Prozentbalken
  samt Angabe „Sprache: x % von y MB" statt eines endlos laufenden Balkens.
- **Die Statuszeile meldet, wenn ein Sprachmodell geladen wird** – der
  Moment, in dem die erste Bereinigung bisher sekundenlang eingefroren
  aussah.
- **Das Taskleistensymbol zeigt den aktiven Zwischenablage-Wächter
  deutlicher**: helleres Grün und ein Leuchtpunkt statt eines bloßen
  Farbtonwechsels.
- **Der Fenstertitel kommt ohne Versionsnummer aus** – im Titel veraltet sie
  unbemerkt; wer sie braucht, findet sie unter „Über dieses Programm".
- **Die Aktualisierung heißt jetzt überall „prüfen"** („Beim Start nach
  Aktualisierungen prüfen", „Jetzt prüfen") statt des schiefen „nachsehen".
- **Deutlich mehr wird gefunden.** Über eine Prüfsammlung aus 144 Dokumenten in
  zwölf Sprachen gemessen, stieg der Anteil der zuverlässig entfernten Angaben
  von 78 % auf 88 %; bei Word- und OpenOffice-Dateien von 70 % auf 87 %. Für
  Deutsch und Italienisch werden im Prüfbestand inzwischen alle bekannten
  Angaben entfernt.
- **Wird ersatzweise mit einer anderen Sprache gearbeitet, steht das im
  Ergebnis.** E-Mail-Adressen, Telefon-, Konto- und Ausweisnummern werden auch
  dann zuverlässig gefunden – Namen und Ortsangaben nicht. Darauf wird jetzt
  ausdrücklich hingewiesen, statt Verlässlichkeit vorzutäuschen.
- **Bilder aus der Zwischenablage behalten ihre Auflösung.** Bisher kamen sie
  in einer neu berechneten, gröberen Fassung zurück.
- **Bilder in Präsentationen**, die aus der Foliengestaltung stammen und damit
  auf jeder Folie erscheinen, werden als solche erkannt und entfernt statt nur
  geschwärzt.

### Behoben

- **Fehlt die Texterkennungs-Maschine, sagt das Programm es jetzt klar** –
  bisher meldete der Hinweis „Texterkennung bereit", sobald nur die
  Sprachdateien da waren, auch wenn Tesseract selbst fehlte und Bilder
  deshalb gar nicht geprüft werden konnten.
- **„Bereinigte Dateien danach öffnen" schweigt nicht mehr, wenn es nicht
  geht**: Kennt Windows für den Dateityp kein Programm (häufig bei `.eml`
  ohne eingerichtetes Mailprogramm), steht das jetzt in Statuszeile und
  Einzelheiten – vorher tat das Häkchen scheinbar nichts.
- **Ein Fehler in einer einzelnen Anzeige friert nicht mehr das ganze
  Fenster ein**: Die Ereignisschleife arbeitet weiter und schreibt den
  Fehler in die Einzelheiten.

- Geschwärzte Bilder in PDF-Dateien konnten unter Umständen als schwarze Fläche
  erscheinen, statt nur an den betroffenen Stellen geschwärzt zu sein.
- In einem seitenfüllenden Hintergrundbild wurde versehentlich auch der darüber
  gedruckte Fließtext mitgeschwärzt.
- Namen, die im Dokument in Großbuchstaben stehen, wurden häufiger übersehen
  als solche in gemischter Schreibweise.
- Bei PDF-Dateien blieben Zeichnungen und Grafiken erhalten, die zuvor mit
  entfernt wurden, wenn sie sich mit einer geschwärzten Stelle überschnitten.
- Ein Platzhalter konnte über ein Symbol oder eine Trennlinie geschrieben
  werden, die unmittelbar neben oder zwischen den ersetzten Wörtern stand.
  Beides wurde dadurch unleserlich. Platzhalter weichen solchen Stellen jetzt
  aus und werden lieber kleiner gesetzt – oder, wenn kein lesbarer Platz mehr
  bleibt, durch einen schwarzen Balken ersetzt.

### Unter der Haube

- Die Verarbeitung von PDF-Dateien wurde vollständig neu aufgebaut. Für die
  Anwendung ändert sich nichts an der Bedienung; das Ergebnis ist bei gleicher
  Trefferquote **rund ein Fünftel schneller**, und jede Bereinigung wird
  anschließend nachgeprüft. Bleibt wider Erwarten etwas stehen, wird die
  betroffene Seite in ein Bild umgewandelt, damit nichts durchrutscht – der
  Text bleibt dabei durchsuchbar und die Darstellung unverändert.

---

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
