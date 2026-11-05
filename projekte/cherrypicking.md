# CherryPicking

**Ein Satz:** Ein Konsolidierungs-Repo ohne Code: eine 100-Punkte-Roadmap und zwölf Notion-Seiten, aus denen ein einziger, am Gerät geprüfter Mathe-Tutor entstehen soll.

**Repo:** `https://github.com/smlfg/CherryPicking` (privat)
**Reifegrad:** Plan
**Stack:** Markdown (Roadmap und Notion-Exporte) · ~980 Zeilen · kein Code
**Nutzen:** Verhindert den neunten Neuanfang: nur noch zusammenführen, was belegt ist.
**Belegt:** Die Roadmap ist vollständig: 16 Arbeitspakete mit Akzeptanzkriterien. Mehr ist nicht behauptet.

---

## Kann

- Eine 100-Punkte-Roadmap mit 16 Arbeitspaketen, Akzeptanzkriterien und einer expliziten Sperrliste dokumentieren.
- Zwölf exportierte Notion-Seiten (762 Zeilen) zu früheren Versuchen, Entscheidungen und verworfenen Plänen offline bereitstellen.
- Eine Zielstruktur für `src/cherry/` und `tests/` vorgeben.

## Kann nicht

- Nichts ausführen: Es gibt keinen Quellcode, keinen Build und keine Tests.
- Einmaliger Plan, kein Werkzeug: nichts davon läuft, ohne dass es jemand in Code übersetzt.
- Keines der 16 Arbeitspakete ist begonnen (0/16 Checkboxen).
- Keine der sieben Vorläufer-Codebasen ist integriert; die Roadmap verweist nur auf externe Pfade.

## Beleg

Auszug aus `ROADMAP.md`:

> Über **188 dokumentierte Versuche** und **7 separate Repositories** stand die eigentliche Definition of Done am Ende bei **0 von 3 echten Lernsessions (0/14 Checkboxen)** — obwohl jedes Einzelteil für sich bereits bewiesen war.

## Erklärung

CherryPicking ist kein Programm, sondern ein Plan. Nach 188 dokumentierten Versuchen in sieben Repositories soll hier nur noch das zusammengeführt werden, was am Gerät nachweislich funktioniert: mitschreiben, deterministisch prüfen und kleine Hinweise — keine Lösungen — auf dieselbe Seite schreiben. Das Ziel ist ein Tutor, der drei echte Lernsitzungen auf dem Paper Pro begleitet. Der Wert liegt im bewussten Verzicht: keine neuen Apps, keine Varianten, keine Regeln ohne Test. Gebaut ist davon noch nichts.

## Probleme

- Die Roadmap nennt absolute Pfade (`/Users/samuelfleig/Projects/01_WORK/CherryPicking`), die seit dem Umzug ins Workspace-Verzeichnis nicht mehr stimmen.
- 0 von 16 Arbeitspaketen begonnen; es gibt keine Tests und keine Fixtures, an denen sich der Plan prüfen ließe.
- Ein belegter End-to-End-Lauf fehlt; die Roadmap ist noch nicht in ausführbare Arbeit übersetzt.
