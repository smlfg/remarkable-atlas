# penecho-mac

**Ein Satz:** Eine macOS-Menüleisten-App, die als reines Frontend die Python-CLIs des PenEcho-Vertrags startet, ihren JSON-Ausstoß anzeigt und damit den Tutor ohne Terminal bedienbar macht.

**Repo:** `https://github.com/smlfg/penecho-mac` (privat)
**Reifegrad:** Prototyp
**Stack:** Swift 6 / SwiftUI, macOS 14+ · ~3.750 Zeilen · 43 Tests in 11 Suites
**Nutzen:** Nimmt Terminal und JSON aus dem Alltag: Tablet wählen, starten, Verlauf lesen.

---

## Kann

- Status und Erreichbarkeit des Tablets anzeigen, Notizbücher und Seiten auflisten und standardmäßig die zuletzt geänderte Seite wählen.
- `rm_watch` mit Auslöser, Erkennungsmodell, Stufe 2, Fach oder automatischem Fach und Agentenprofil starten und stoppen; gestoppt wird ausschließlich per SIGINT.
- Den Verlauf einer Session mit erkannten Zeilen, Hinweis, Fehlern und Latenz anzeigen. Unsichere Zeilen werden nie als korrekt oder grün dargestellt.
- Jeden Python-Aufruf über einen Wrapper mit Zeitlimit, JSON-Prüfung und deutschen Fehlermeldungen führen; API-Schlüssel werden in Logs durch `[REDACTED]` ersetzt.
- Einen Testmodus ohne Tablet (`--local`, `--root`) und einen Agenten-Editor bieten, der nur die Feldnamen des CLI-Vertrags schreibt.

## Kann nicht

- Enthält keine Tutor-, SSH- oder `.rm`-Logik. Ohne das separate `algebra-agent`-Repo und dessen Python-CLIs funktioniert die App nicht.
- Schreibt nicht selbst auf das Tablet und speichert keinen API-Key — das übernehmen die CLIs.
- Ist nicht notarisiert; `make-app.sh` baut ein lokales Bundle mit Ad-hoc-Signatur.
- Gilt laut eigener Definition erst nach drei Sessions mit je drei Turns als „erprobt"; im Repo liegen keine solchen Session-Logs.

## Erklärung

Die App ist die Fernbedienung für den PenEcho-Tutor auf dem Mac. Sie zeigt in der Menüleiste, ob das Tablet erreichbar ist, lässt Notizbuch, Seite, Fach, Modell und Agent auswählen und startet oder beendet den Beobachter. Während einer Session macht sie sichtbar, welche Zeilen erkannt wurden, welchen Hinweis der Agent gegeben hat und wie lange es gedauert hat. Der eigentliche Tutor steckt nicht in dieser App, sondern in der Python-Seite; die App macht ihn nur bedienbar und nachvollziehbar.

## Probleme

- Der Reifegrad ist offen: Die README verlangt drei Sessions mit je drei Turns ohne Absturz, im Repo ist kein entsprechender Nachweis enthalten.
- Die App hängt an einem Vertrag in einem anderen Repo. Der letzte Commit ist eine Doku-Korrektur dazu, dass der Vertrag umgezogen ist — die Kopplung bleibt eine driftende Abhängigkeit.
- Es gibt nur einen lokalen Ad-hoc-Build; Signierung, Notarisierung und Verteilung an andere Macs sind nicht eingerichtet.
- Ein Gerätetest der App selbst ist nicht dokumentiert; die Tests laufen ohne Tablet gegen ein nachgebautes CLI-Repo.
