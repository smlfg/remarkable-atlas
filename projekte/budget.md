# budget

**Ein Satz:** Eine Transportschicht, die beim Zurückschreiben nur den neuen Byte-Tail aufs Tablet schickt und einen Turn in Requests, Bytes und Bildtokens misst.

**Repo:** `https://github.com/smlfg/remarkable-budget-mac` (privat)
**Reifegrad:** Werkzeug
**Stack:** Python 3 (nur Standardbibliothek) und POSIX-Sh · ~800 Zeilen Produktivcode · 41 Tests
**Nutzen:** Macht die zwei echten Engpässe sichtbar: Tageskontingent und Übertragungszeit.
**Belegt:** 41 Tests ohne Gerät, Netz oder Modell; die Invariante `out = base + Tail` ist byteweise geprüft.

---

## Kann

- Die Invariante `out = base + Tail` byteweise prüfen, ohne das `.rm`-Format zu parsen.
- Beim Writeback nur den Tail übertragen: Digest-Gate vor dem Schreiben, Backup auf dem Gerät, `cat base tail` plus atomares `mv`, zweites Digest-Gate mit Rollback.
- Für SSH und lokal denselben Shell-Skripttext nutzen; der Konflikt-Schutz verhindert das Überschreiben neuer Schülertinte.
- Requests, Leitungsbytes, Bildtokens und Sekunden zählen; `DailyBudget` bildet 20 Requests pro Tag nach, `pngcost` liest PNG-Maße aus dem IHDR ohne Pillow.
- Die CLI `split`, `compare`, `fetch`, `push`, `verify`, `pngcost`, `quota` bereitstellen — 41 Tests ohne Gerät, Netz oder Modell.

## Kann nicht

- Der SSH-Weg gegen ein echtes Paper Pro ist ungeprüft; nur der lokale Transport ist getestet.
- Ob xochitl eine per Tail ergänzte Datei korrekt anzeigt, ist nicht belegt — belegt ist nur der Weg über die ganze Datei.
- Ist in `pur` oder `algebra-agent` nicht eingebaut; im Workspace importiert niemand `budget`.
- Versteht weder `.rm`-Inhalt noch Handschrift; es ist Transport- und Kostenmessung, keine Erkennung.

## Beleg

`python3 -m budget quota --limit 20 --requests-per-turn 3` — echte Ausgabe:

```
modell     gemini-flash-lite-latest
limit      20 Requests/Tag
pro Turn   3 Requests
turns      6 (bei 3 h und 20 min Abstand)
```

## Erklärung

`budget` nutzt eine Eigenschaft des `.rm`-Formats: Eine geänderte Seite ist byteweise die alte Seite plus ein Anhang. Statt die ganze Datei erneut zu übertragen, schickt das Werkzeug nur diesen Anhang und prüft vorher und nachher per SHA-256, dass auf dem Tablet nichts anderes liegt. Zusätzlich zählt es, was ein Durchlauf kostet — Modellaufrufe, übertragene Bytes, Bildtokens und Zeit. Das ist für ein Gerät mit USB-Verbindung und ein knappes Tageskontingent nützlich, weil es die beiden Engpässe sichtbar macht, statt sie zu schätzen.

## Probleme

- Der SSH-Weg gegen ein echtes Paper Pro ist nicht verifiziert.
- Die Anzeige einer tail-angereicherten Datei durch xochitl ist offen.
- Die Integration in den Live-Loop fehlt; der alte Weg in `rm_watch.py` bleibt aktiv.
- Die Ersparnis ist an zwei Gerätedateien gemessen, nicht über mehrere Turns.
