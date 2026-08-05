# PII Cleaner – Freigaben

Dieses Repository enthält **ausschließlich Freigabedateien**: je Ausgabeweg
eine Beschreibungsdatei und die zugehörigen Installationspakete. Der Quelltext
des Programms liegt nicht hier.

| Datei | Ausgabeweg |
|---|---|
| `stable.json` | stabile Fassungen |
| `beta.json` | Vorabfassungen |
| `nightly.json` | Tagesfassungen |

Jede Beschreibungsdatei ist mit Ed25519 signiert; der öffentliche Schlüssel
steckt im Programm. Eine Datei ohne gültige Signatur wird abgelehnt – ebenso
eine, deren Prüfsumme nicht stimmt oder die über eine ungesicherte Verbindung
käme.

Wer eine dieser Dateien verändert, ohne den privaten Schlüssel zu besitzen,
macht sie damit unbrauchbar. Genau das ist der Zweck.
