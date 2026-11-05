# penecho-lens

**Ein Satz:** Eine macOS-Beobachter-App, die den PenEcho-Ablauf sichtbar macht: Sie liest entweder das Protokoll einer laufenden Session oder startet den Trace der Python-Pipeline auf einer lokalen `.rm`-Seite und zeigt jeden Schritt.

**Repo:** https://github.com/smlfg/penecho-lens (privat)
**Reifegrad:** Werkzeug
**Stack:** Swift 6 / SwiftUI, macOS 14+ · ~2.600 Zeilen · 18 Tests in 5 Suites

---

## Kann

- Im Live-Modus dem neuesten Session-Log unter `~/penecho-logs` folgen, es alle zwei Sekunden neu lesen und Ereignisse in deutsche Sätze übersetzen.
- Die Seite als Bild zeigen, dazu erkannte Zeilen mit Boxen, den Turn, die Schreibkette und rohe Ereignis-JSONs.
- Im Simulationsmodus `python -m algebra_agent.trace` auf einer gewählten `.rm`-Seite starten und Seitenbild, Stufen, Modellaufrufe mit Dauer und Tokenzahlen sowie das Schreibziel anzeigen.
- Simulationsergebnisse in eine separate `*.trace-out.rm` schreiben, nicht in die Originalseite — und warnen, wenn sich die Zahl der Schülertinte verändert.
- Die Modellliste über die CLI des Repos laden und Repo-Pfad sowie Python-Interpreter über `PENECHO_REPO`, UserDefaults oder Standardpfad auflösen.

## Kann nicht

- Steuert das Tablet nicht und schreibt nicht zurück; sie beobachtet nur.
- Läuft nicht allein: Ohne `algebra-agent`-Checkout mit `trace`-CLI und passender Python-Umgebung passiert nichts.
- Hat kein README und ist nicht im CLI-Vertrag verankert; die Schnittstelle ist nur über den Trace-Code definiert.
- Kann die Sichtbarkeit der Tinte nicht selbst bestätigen; sie gibt weiter, was im Log steht, und markiert Unbestätigtes als solches.

## Bild

kein Bild vorhanden.

## Erklärung

Die App ist ein Fenster in die Maschine: Sie zeigt, was der Agent gerade tut, statt nur ein Ergebnis anzuzeigen. Im Live-Betrieb liest sie mit, was eine laufende Session protokolliert; im Simulationsbetrieb rechnet sie eine Seite einmal durch und legt jeden Schritt offen. Das ist vor allem beim Entwickeln und Fehlersuchen nützlich, weil man sieht, ob das Problem beim Lesen, beim Urteilen oder beim Schreiben liegt. Für den normalen Lernbetrieb ist sie nicht gedacht.

## Probleme

- Es gibt keine README und keine weitere Dokumentation; der einzige Commit ist ein Initial-Commit vom 25.10.
- Die App steht nicht im CLI-Vertrag. Die Projektordnung führte sie als „noch nicht im Vertrag" — daran hat sich im Repo nichts Erkennbares geändert.
- Die 18 Tests prüfen Protokoll-Dekodierung, Puffer und Argumente, aber nicht die Oberfläche und nicht den Lauf gegen ein echtes Gerät.
- Die Live-Ansicht hängt an fremden Logs; ob geschriebene Tinte tatsächlich sichtbar ist, kann sie nicht unabhängig prüfen.
