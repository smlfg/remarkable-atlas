# reMarkable-Portfolio

**Handschrift, Stift, Feedback — ohne den Lernfluss zu verlassen.**

Dieses Repo bündelt 16 eigene Projekte rund um das reMarkable Paper Pro. Der rote Faden: Ein Blatt Papier soll rechnen können. Wer eine Aufgabe schreibt, bekommt einen kurzen Hinweis neben der eigenen Handschrift — kein Chatfenster, kein Handy, keine App dazwischen.

Der Weg dahin war nicht gerade. 188 dokumentierte Versuche, sieben Vorläufer-Codebasen, zwei Retrospektiven. Was hier steht, ist deshalb nicht die Erfolgsgeschichte, sondern der belastbare Teil davon: was funktioniert, was nicht, und woran man es erkennt.

![Ausschnitt: rote Unterstreichung unter der ersten falschen Zeile](media/algebra-agent-vergleich.png)

---

## Die Projekte

| # | Projekt | Was es kann | Reifegrad | Links |
|---|---|---|---|---|
| 1 | **algebra-agent** | Liest die Seite, findet den ersten falschen Rechenschritt, schreibt einen Hinweis als Tinte daneben. | Prototyp | [Detail](projekte/algebra-agent.md) · [Repo](https://github.com/smlfg/algebra-agent) |
| 2 | **penecho** | Der Produktvertrag: sechs prüfbare Punkte, die erfüllt sein müssen, bevor von einem Tutor die Rede ist. | Dokument | [Detail](projekte/penecho.md) · [Repo](https://github.com/smlfg/penecho) |
| 3 | **penecho-mac** | Menüleisten-App, die den Tutor ohne Terminal bedienbar macht. | Prototyp | [Detail](projekte/penecho-mac.md) · [Repo](https://github.com/smlfg/penecho-mac) |
| 4 | **penecho-lens** | Fenster in die Maschine: zeigt Schritt für Schritt, was der Agent gerade tut. | Werkzeug | [Detail](projekte/penecho-lens.md) · [Repo](https://github.com/smlfg/penecho-lens) |
| 5 | **inkpartner** | Denkt sich einen Lehrer mit Rotstift: Haken, Kreis, Fragezeichen — nach festen Regeln, nicht nach Modelllaune. | Prototyp | [Detail](projekte/inkpartner.md) · [Repo](https://github.com/smlfg/inkpartner) |
| 6 | **underline** | Unterstreicht die falsche Zeile rot und hakt richtige grün ab, ohne die Handschrift anzutasten. | Prototyp | [Detail](projekte/underline.md) · [Repo](https://github.com/smlfg/remarkable-underline-mac) |
| 7 | **pur** | Eine Seite, ein lokales Modell, ein angehängter Text. Ohne Cloud, ohne Konto. | Prototyp | [Detail](projekte/pur.md) · [Repo](https://github.com/smlfg/remarkable-pur-mac) |
| 8 | **budget** | Schickt beim Zurückschreiben nur den neuen Byte-Anhang und zählt Requests, Bytes und Tokens. | Werkzeug | [Detail](projekte/budget.md) · [Repo](https://github.com/smlfg/remarkable-budget-mac) |
| 9 | **keepitsimple** | Messplatz: liest den Stiftstrom live mit und stellt mehrere Tutor-Antworten zum Blindvergleich. | Werkzeug | [Detail](projekte/keepitsimple.md) · [Repo](https://github.com/smlfg/keepitsimple) |
| 10 | **mlops-gedanken** | Laborbuch: 18 echte Seiten, Ground Truth, Benchmarks — und der Nachweis, welche Pipeline-Stufe wirklich trägt. | Werkzeug | [Detail](projekte/mlops-gedanken.md) · [Repo](https://github.com/smlfg/mlops-gedanken-umsetzung) |
| 11 | **algebra-graveyard** | Chronik des Scheiterns: 188 Versuche, 13 Fehlermuster, 15 Lehren — jeder Satz mit Beleg. | Archiv | [Detail](projekte/algebra-graveyard.md) · [Repo](https://github.com/smlfg/algebra-graveyard) |
| 12 | **remarkable-graveyard** | Dieselbe Idee kompakt: 25 Versuche, 69 Fehler, 34 Sackgassen in einer Offline-Seite. | Archiv | [Detail](projekte/remarkable-graveyard.md) · [Repo](https://github.com/smlfg/remarkable-graveyard) |
| 13 | **skills-paper-pro** | Zehn beschriebene Arbeitsabläufe vom Verbinden bis zum Feedback-Schreiben. | Dokument | [Detail](projekte/skills-paper-pro.md) · [Repo](https://github.com/smlfg/skills-paper-pro) |
| 14 | **rm-drill** | Mitschnitt einer Prüfungsvorbereitung: Frage wird vorgelesen, Antwort aufs Tablet gemalt, Agent liest zurück. | Archiv | [Detail](projekte/rm-drill.md) · [Repo](https://github.com/smlfg/rm-drill-mac) |
| 15 | **remake-website** | Portfolio als nachgebauter Mac-Desktop im Browser: Sperrbildschirm, Dock, Fenster. | Prototyp | [Detail](projekte/remake-website.md) · [Repo](https://github.com/smlfg/remake-website) |
| 16 | **CherryPicking** | Der Plan für danach: nur noch zusammenführen, was am Gerät belegt ist. | Plan | [Detail](projekte/cherrypicking.md) |

---

## Reifegrad

Die Skala ist absichtlich streng. „Fertig" heißt hier: auf dem Gerät belegt, nicht: Tests grün.

| Stufe | Bedeutung |
|---|---|
| **Produkt** | Auf dem Gerät erprobt und im Alltag benutzbar. *(derzeit von keinem Projekt erreicht)* |
| **Prototyp** | Die Technik läuft nachweislich; der Gerätebeleg oder die Dauererprobung fehlt. |
| **Werkzeug** | Für Entwicklung, Messung oder Fehlersuche gebaut — nicht für Endnutzer. |
| **Dokument** | Vertrag, Doku oder Nachschlagewerk. Kein ausführbarer Code. |
| **Archiv** | Abgeschlossen. Rückblick, keine Weiterentwicklung. |
| **Plan** | Noch kein Code. |

---

## Der Kern in einem Absatz

`algebra-agent` ist das einzige Projekt, das den ganzen Kreis schließt: Seite lesen, Schritt prüfen, Tinte zurückschreiben. Alles andere ist entweder Zulieferer (`pur`, `underline`, `budget`, `inkpartner`), Messgerät (`keepitsimple`, `mlops-gedanken`), Bedienoberfläche (`penecho-mac`, `penecho-lens`), Vertrag (`penecho`) oder Rückblick (`algebra-graveyard`, `remarkable-graveyard`). Der Tutor selbst steht bei **0 von 3** erprobten Sitzungen — das ist der ehrliche Stand.

---

## Fremde Projekte

Zwei Ordner im Workspace sind **nicht** eigene Arbeit und stehen hier nur als Referenz:

- [`smart_remarkable`](referenzen.md#smart_remarkable) — Rust-Agent von Yang Wu, Fork von `awwaiid/ghostwriter`.
- [`math-vision`](referenzen.md#math-vision) — Rust-CLI von Mikail Plotzky.

Beide sind im Abschnitt [Referenzen](referenzen.md) beschrieben, mit klarer Herkunftsangabe.

---

## Sichtbarkeit

Fast alle Repos sind **privat**. Ein öffentliches Portfolio mit Links auf private Repos führt ins Leere (404). Vor einer Veröffentlichung muss entschieden werden:

1. Portfolio privat lassen und als interne Landkarte nutzen, **oder**
2. ausgewählte Repos öffentlich schalten (mindestens `algebra-agent`, `penecho`, `keepitsimple`) **oder**
3. das Portfolio öffentlich machen und nur die bereits öffentlichen Projekte verlinken (`inkpartner`).
