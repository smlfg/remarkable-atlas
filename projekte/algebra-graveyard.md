# algebra-graveyard

**Ein Satz:** Eine statische Website mit fest eingebettetem Datensatz, die die Versuche, Fehlschläge und Entscheidungen beim Bau des Algebra-Tutors vom 17. bis 25.10.2026 belegt aufarbeitet.

**Repo:** https://github.com/smlfg/algebra-graveyard (privat)
**Reifegrad:** Archiv
**Stack:** HTML, CSS, Vanilla JavaScript ohne Build-Schritt; Python 3 für die Datensatz-Werkzeuge · ~3.900 Zeilen · 0 Tests

---

## Kann

- Zehn Ansichten bereitstellen: Timeline, Dead Ends, Failure Map, Current State, Decisions, Patterns & Lessons, Evidence, Evidence Gaps, Documents und Next Build.
- 188 Versuche, 42 bewertete Komponenten, 79 Entscheidungen, 13 Fehlermuster, 15 Lehren, 16 Evidenzlücken und 482 Belege anzeigen. Jeder Beleg trägt Fundstelle, Zitat und Marker (`BELEGT`, `GERAET`, `HYPOTHESE`, `OFFLINE`).
- Die Failure Map als SVG-Kraftgraphen mit 264 Knoten rendern: Ziehen, Zoomen, Klick isoliert die Nachbarschaft, Umschalten auf „failures only".
- Über sieben Dimensionen filtern (Suche, Komponente, Kategorie, Ergebnis, Konfidenz, Track, Zeitraum) und einzelne Versuche per Deep-Link wie `#att-033` direkt öffnen.
- Den Datensatz unabhängig von der Website als `data/dataset.json` bereitstellen und mit `tools/check_evidence.py` jeden Beleg gegen die Primärquelle prüfen.

## Kann nicht

- Keine Live-Daten und kein Backend: Der Datensatz ist auf dem Stand 25.10.2026 eingefroren; neue Sitzungen werden nicht automatisch importiert.
- Filter wirken nur auf Timeline und Dead Ends; alle anderen Ansichten zeigen immer alles.
- Keine Tests und kein CI; die einzige Prüfung ist `check_evidence.py`, und die braucht die Quellordner außerhalb des Repos.
- Der Rebuild ist nicht vollständig reproduzierbar: zwei Extraktionsskripte lesen `/tmp/ink-attempts`, ein Tool hardcodet den Pfad des Schwester-Repos.

## Bild

kein Bild vorhanden.

## Erklärung

Statt Erfolge zu feiern, hält dieses Projekt fest, was beim Bau des Mathe-Tutors schiefging und warum. Jeder Eintrag verweist auf Commit, Sitzungsprotokoll oder Dokument, damit eine Behauptung nachprüfbar bleibt. Die Website macht daraus eine durchsuchbare Chronik mit Fehlerkarte und einer Liste der Lücken, die sich nicht belegen ließen. Nützlich ist das für die nächste Person oder den nächsten Agenten, der nicht dieselben Irrtümer wiederholen soll. Es ist ausdrücklich ein Rückblick, kein laufendes System.

## Probleme

- Die wichtigste Konstante des Projekts ruht auf einer Prosa-Zusammenfassung: Die Kalibrierungs-Fixture hat eine leere Per-Page-Liste, und die `.rm`-Kalibrierungsdateien sind per `.gitignore` gar nicht eingecheckt.
- Die Dokumentation widerspricht dem gemessenen Zustand: Ein Task-Dokument nennt 648 grüne Tests und einen sauberen Baum; gemessen wurden 863 Testmethoden mit 19 Fehlschlägen sowie 24 modifizierte und 14 unversionierte Dateien.
- Der schwerste dokumentierte Defekt (`stepcheck` prüft gegen die Originalgleichung) ist im Datensatz beschrieben, aber nicht behoben — die Empfehlung liegt im Nachbar-Repo.
- Die Zuordnung im Tab „Next Build" ist ausdrücklich eine Bewertung des Rückblicks, keine vom Projekt getroffene Entscheidung.
