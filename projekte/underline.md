# underline

**Ein Satz:** Ein Agent, der auf einer Paper-Pro-Seite die falsche Zeile rot unterstreicht und richtige Zeilen grün abhakt, ohne die Tinte des Schülers zu verändern.

**Repo:** `https://github.com/smlfg/remarkable-underline-mac` (privat)
**Reifegrad:** Prototyp
**Stack:** Python 3, rmscene, Pillow, Ollama · ~2.450 Zeilen Produktivcode · 54 Tests
**Nutzen:** Die kleinste sinnvolle Rückmeldung: eine Linie, ein Haken, ohne die Arbeit zu überschreiben.

---

## Kann

- Eine `.rm`-Seite in Striche zerlegen, zu Zeilen gruppieren und den Text zweifach lesen; nur übereinstimmende Lesungen gelten als bestätigt.
- Die Zeile auf drei Wegen wählen: Mensch (`--select`), feste Regel (`--rule all|question|keyword|uncertain`) oder Modell aus einer Klartext-Anweisung.
- Eine rote Linie unter oder einen grünen Haken neben die Zeile planen, mit 12 px Abstand. Passt nichts, wird nichts geschrieben.
- Die Marken als neue Blöcke in die eigene Ebene „Underline Agent" schreiben; `ununderline` nimmt sie wieder heraus, die Schülertinte bleibt byteweise unverändert.
- 54 Tests laufen mit `--model fake` offline und deterministisch.

## Kann nicht

- Rechnet nicht nach: richtig/falsch kommt aus gelesenem Text und Anweisung, nicht aus einem Rechenmodell.
- Ist am Tablet nicht nachgewiesen; die Tests laufen gegen synthetische Seiten, ein Rückschreiben ist nicht belegt.
- Die grüne Variante ist getestet, aber nie am Gerät gesehen.
- Kennt keine Aufgabensammlung; der Nachweis an fünf echten Vorlesungsaufgaben steht aus.

## Beleg

Die Befehle, die tatsächlich existieren — Stand heute:

```
page         die Seite ansehen
underline    Text unterstreichen
ununderline  eine Unterstreichung wieder zuruecknehmen
device       das Tablet (nur gelesen)
push         Seite zurueck auf das Tablet
```

## Erklärung

Der Agent liest eine handschriftliche Seite, erkennt zusammengehörige Zeilen und entscheidet, welche davon markiert werden soll. Diese Entscheidung kann ein Mensch treffen, eine einfache Regel oder ein Sprachmodell; unleserliche Zeilen werden nie ausgewählt. Die Markierung wird als eigene Ebene in die Datei geschrieben, sodass die ursprüngliche Handschrift unverändert bleibt und sich die Markierung wieder entfernen lässt. Nützlich ist das für Lernende, die Rückmeldung direkt auf der Seite wollen, ohne abzufotografieren oder das Programm zu wechseln.

## Probleme

- Der Agent beurteilt Mathematik nur über das Lesemodell; ein falsch gelesener Schritt kann als richtig oder falsch markiert werden.
- Es gibt keinen Gerätebeleg: Das Rückschreiben ist nicht belegt, die grüne Variante wurde nie am Tablet gesehen.
- Der Nachweis an echten Vorlesungsaufgaben fehlt; die Definition of Done fordert fünf.
