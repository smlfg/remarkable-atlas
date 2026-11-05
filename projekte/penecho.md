# penecho

**Ein Satz:** Der Produktvertrag für einen bidirektionalen E-Ink-Algebra-Tutor — er legt fest, was auf dem Paper Pro passieren muss, bevor von einer funktionierenden Lern-Session die Rede ist.

**Repo:** `https://github.com/smlfg/penecho` (privat)
**Reifegrad:** Dokument
**Stack:** Markdown · ~1.000 Zeilen · kein ausführbarer Code
**Nutzen:** Macht Fortschritt prüfbar. Ohne diese sechs Checkboxen wäre unklar, ob der Tutor funktioniert oder nur läuft.
**Belegt:** Der Vertrag selbst: 13 Abschnitte CLI-Schnittstelle und sechs DoD-Punkte, jeder einzeln prüfbar. Über die Umsetzung sagt das nichts.

---

## Kann

- Die Definition of Done in sechs prüfbaren Punkten formulieren: falsche Distributiv-Aufgabe, bewusster Auslöser, kurzer Hinweis als Stiftstriche, erhaltene Handschrift, drei Mensch-Agent-Wechsel, gemessene Latenz.
- Eine zweite Stufe fordern: rot/grün, richtige Position, fünf echte Vorlesungsaufgaben — und nahtloses Zurückschreiben ohne Neustart der Notizoberfläche.
- Den CLI-Vertrag über 13 Abschnitte festhalten: Erreichbarkeit, Notizbücher, Fächer, Modelle, Schrift, Agenten, Sessions, `rm_watch` und weitere. Das ist die gemeinsame Schnittstelle für App und Python-Implementierung.
- Produktgrenzen setzen: gleiche Seite, keine gelöschte Handschrift, kleinste hilfreiche Hilfe, kein falsches Grün, keine erfundenen Gerätemessungen.
- Setup, Timebox, Abbruch- und Rückgabekriterien dokumentieren und die drei Ebenen Produktvertrag, Implementierung und Client einander zuordnen.

## Kann nicht

- Enthält keinen ausführbaren Code und keine Tests. Die Tutor-Logik liegt im separaten Repo `algebra-agent`.
- Belegt die Definition of Done nicht: Alle 14 Checkboxen im README sind offen.
- Nahtloses Zurückschreiben ohne Neustart von `xochitl` ist nicht gebaut — und der CLI-Vertrag führt es unter „Was NICHT gebaut wird", während das README es als Produktstufe fordert.
- Kein Notion-Sync, keine Accounts, keine Einstellungsseiten, keine Installation auf dem Tablet — alles bewusst ausgeschlossen.

## Beleg

Auszug aus der Definition of Done — alle Punkte sind im Repo noch offen:

> - [ ] Ich schreibe `3(x+2)=15` und darunter den falschen Schritt `3x+2=15`.
> - [ ] Ich löse den Agenten **bewusst** aus. Er schreibt nicht ungefragt dazwischen.
> - [ ] Der Agent erkennt den Fehler (Distributivgesetz) und schreibt einen **kurzen Hinweis** als Stiftstriche auf dieselbe Seite.
> - [ ] Meine Schrift bleibt stehen. Nichts von mir wird überschrieben oder gelöscht.
> - [ ] Mindestens **3 Wechsel** Mensch → Agent → Mensch auf derselben Seite funktionieren.
> - [ ] Gemessen: Zeit vom Auslösen bis zum ersten Agentenstrich.

## Erklärung

Dieses Repository enthält keine Software, sondern die Vereinbarung darüber, was die Software können muss. Es beschreibt den Lernkreis aus Schreiben, Erkennen, kurzem Hinweis und Weiterschreiben auf derselben Seite — und macht ihn in prüfbaren Punkten abhakbar. Für die Entwicklung ist das der eigentliche Wert: Mensch und Agent bauen nicht aneinander vorbei, und jeder Fortschritt muss am Gerät belegt werden. Der Preis ist Ehrlichkeit — solange die Checkboxen leer sind, ist der Tutor ein Versprechen, kein Produkt.

## Empirischer Beleg für die Lösungsregel (05.11.2026)

Im 18a-Benchmark trat `penecho_musterloesung` als bewusste Gegenprobe an — eine Variante, die die Regel „keine Lösung verraten“ durch eine vollständige Musterlösung ersetzt und kein Produktkandidat ist. Sie verrät in beiden Schülerständen die Lösung (2/2) und ist in beiden fachlich falsch (2/2): Im offenen Fall fehlt `17π/6`, im Fehlerfall ist die genannte `L₂`-Menge falsch. Technisch zählt sie trotzdem als `ok`, weil der Benchmark nur technische Gültigkeit prüft, nicht fachliche Richtigkeit.

Damit ist die Regel „keine Lösung verraten“ empirisch gestützt: Die verratene Lösung war in beiden Fällen falsch, und die technische Prüfung erkannte keinen der beiden Fehler. Der Befund bleibt eine Fallserie — eine Aufgabe, ein Richter, ein synthetischer Schülerstand, keine Lernwirkung, ein Modell. Messplatz und Rohdaten im Repo [`keepitsimple`](keepitsimple.md): `docs/BENCHMARK-18A-2026-11-05.md`, `docs/BENCHMARK-18A-FEHLER-2026-11-05.md`, `arena/runs/benchmark-18a-2026-11-05.jsonl`, `arena/runs/benchmark-18a-fehler-2026-11-05.jsonl`.

## Probleme

- Die Definition of Done ist offen; im Repo gibt es keinen Nachweis für drei Wechsel oder eine gemessene Latenz auf dem Gerät.
- Das nahtlose Zurückschreiben ist nur als Anforderung dokumentiert, während CLI-Vertrag und Projektordnung es ausschließen. Der Widerspruch ist nicht aufgelöst.
- Die Timebox in `SETUP.md` ist ein leeres Formular — tatsächliche Setup-Dauer und Lieferdaten fehlen.
- Die Projektordnung ist veraltet: Sie führt `penecho-lens` noch als „kein Repo", obwohl es seit dem 25.10. eines gibt.
