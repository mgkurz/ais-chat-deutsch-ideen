# STATUS.md, Projektstand

Stand: 09.09.2026

## Wo das Projekt steht

Die Seite ist fertig und veröffentlicht: 42 Beispiele in einer einzigen `index.html`, live über GitHub Pages, erreichbar über `t1p.de/ais-chat-deutsch`. Es ist ein laufendes Artefakt, kein Neubau. Arbeit daran ist Pflege.

Letzter Commit vor dieser Session: `3a772fa` „Update copyright year in LICENSE file" vom 21.05.2026. Davor `c6054e8` vom selben Tag, der den Kopier-Button je Beispiel eingeführt und die Filter neu gegliedert hat.

## In dieser Session (09.09.2026)

- Projektdoku angelegt: `CLAUDE.md` (aus der Vorlage), `CLAUDE.local.md` (gitignored), `ORTE.md`, diese Datei. Das Repo hatte bis dahin keine `.gitignore`, jetzt schon.
- `a4852cd` **Beispiel 16 „Argumentations-Trainer" fachlich überarbeitet.** Ersetzt durch die geprüfte Fassung aus `~/Projekte/ausbildungskraefte-deutsch/erprobung/hintergrund/beispiel-16-ersatzzeile.txt`. Behoben sind die sechs Befunde aus `beispiel-16-pruefung.md`: uneinheitliche Begriffe, „Beispiel" statt des Oberbegriffs Stützung, fehlende Bewertungskriterien, Zirkelschluss nicht genannt, kein Abbruch, generisches Maskulinum. Tags und Inklusions-Variante sind unverändert, eine Klassenstufe steht nicht im Text.
- `a4f34d6` **PLZ korrigiert**, 35389 auf 35398, an beiden Stellen (Impressum und Datenschutzerklärung).
- `7a052cd` **ORTE.md korrigiert.** Die Datei behauptete fälschlich, es gebe keine Git-Tags zum Projekt.
- **Veröffentlicht.** Push nach `origin/main`, Tag `v1.1.1` gesetzt, GitHub-Release [v1.1.1](https://github.com/mgkurz/ais-chat-deutsch-ideen/releases/tag/v1.1.1) angelegt, Pages-Build durchgelaufen. Live-Seite und Kurzlink `t1p.de/ais-chat-deutsch` gegengeprüft: byte-identisch mit HEAD, PLZ 35398 an beiden Stellen, Beispiel 16 in der neuen Fassung.

Geprüft nach beiden Änderungen: `DATA`-Array syntaktisch in Ordnung, 42 Einträge, IDs 1 bis 42 lückenlos, 12 Inklusions-Einträge. Im Browser: 42 Karten, Zähler „42 von 42", Karte 16 klappt auf und zeigt alle drei Blöcke, Filter Sek I plus Lernszenario liefert 4 Treffer inklusive Beispiel 16, Kopier-Button liefert den erwarteten Text, Impressum und Datenschutzerklärung zeigen 35398.

## Achtung: Live-Einsatz am 10.09.2026

**Die Seite wird am 10.09.2026 live in einer Demo benutzt**, beim Forum der Ausbildungskräfte Deutsch. Sie ist dort Ausgangspunkt: Ein Beispiel wird per Kopier-Button aus der Sammlung geholt und weiterverarbeitet. Deshalb gilt bis dahin und generell:

- Jede Änderung am `DATA`-Array vor dem Öffnen der Seite als JavaScript gegenlesen. Ein einziges unescaptes Zeichen bricht das ganze Array, und dann ist die Seite **komplett leer**, nicht nur ein Eintrag defekt. Der Testweg steht in `CLAUDE.md`, Abschnitt „Beispiele pflegen".
- Nach jeder Änderung die Seite lokal öffnen und den geänderten Eintrag wirklich anfassen: aufklappen, filtern, kopieren.
- Kurz vor der Veranstaltung nichts mehr anfassen, was nicht getestet ist.

## Offene Punkte

- **Release-Kopie in der Ablage fehlt.** `~/Documents/Arbeit/MediaLab/AIS.chat/Github/ais-chat-deutsch-ideen/` hat Ordner für `v1.0.0` und `v1.1.0`, aber keinen für `v1.1.1`. Zu entscheiden: neuen Ordner anlegen oder die Ablage-Kopien aufgeben und in `ORTE.md` allein auf GitHub und die Git-Tags verweisen. Der zweite Weg wäre konsequenter, seit die Versionen sauber als Tags im Repo stehen.
- **Diese Datei liegt hinter dem Tag.** Der Eintrag zur Veröffentlichung ist erst nach `v1.1.1` committet, das Release enthält ihn nicht. Bei künftigen Releases STATUS.md vor dem Tag nachziehen.
- **`README.md` nicht angefasst.** Sie beschreibt die Feldstruktur, erwähnt aber nicht, dass das Feld `category` von Rendering und Filter nicht ausgewertet wird. Kleinigkeit, kein Handlungsdruck.
