# ORTE.md, Wegweiser zu externen Orten

Dieses Repo ist Produktionsort und Quelle der Wahrheit für die `index.html` und die Doku. Hier steht, wo die Seite sonst noch auftaucht und woher Zulieferungen kommen. Stand: 09.09.2026.

## Veröffentlichung

| Was | Wo |
| --- | --- |
| Repo (öffentlich) | GitHub `mgkurz/ais-chat-deutsch-ideen`, <https://github.com/mgkurz/ais-chat-deutsch-ideen> |
| Live-Seite | GitHub Pages, <https://mgkurz.github.io/ais-chat-deutsch-ideen/>, gebaut aus `main` |
| Kurzlink | `t1p.de/ais-chat-deutsch` (in Material, Folien und QR-Codes der verwendete Weg) |

## Release-Kopie

| Was | Wo |
| --- | --- |
| v1.1.0, Stand 21.05.2026 | `~/Documents/Arbeit/MediaLab/AIS.chat/Github/ais-chat-deutsch-ideen/v1.1.0/` |
| v1.0.0, ältere Ablage | `~/Documents/Arbeit/MediaLab/AIS.chat/Github/ais-chat-deutsch-ideen/v1.0.0/` |

**Wichtig, Versionsnummern:** In der `index.html` steht **keine** Versionsnummer. Die Bezeichnung „v1.1.0" existiert ausschließlich als Ordnername in der Ablage oben und in fremder Doku (`ORTE.md` des Projekts `ausbildungskraefte-deutsch`). Sie ist nicht aus dem Repo ableitbar, es gibt auch keinen Git-Tag dazu. Wer eine Version nennen will, muss sie an dieser Stelle nachschlagen oder besser den Commit-Hash verwenden.

Die `index.html` in `v1.1.0/` war beim Anlegen dieser Datei byte-identisch mit HEAD (`3a772fa`). Die `LICENSE` dort ist älter: der Commit `3a772fa` vom 21.05.2026 hat die Copyright-Zeile nachgezogen, die Ablage-Kopie hat noch den Wortlaut davor.

## Verwandte Projekte

| Projekt | Beziehung | Ort |
| --- | --- | --- |
| `ais-chat-config` | Schwesterprojekt, die drei Config-Prompts (Lernszenario, Dialogpartner, Assistent). **Der Kopier-Button dieser Seite arbeitet darauf hin**: Er liefert ein Beispiel als Klartext, der dann in einen dieser Prompts eingesetzt wird. Ist im Footer der README verlinkt. | `~/Projekte/ais-chat-config/`, GitHub `mgkurz/ais-chat-config`, Kurzlink `t1p.de/ais-chat-config` |
| `ausbildungskraefte-deutsch` | Nutzendes Projekt, Forum der Ausbildungskräfte Deutsch am 10.09.2026. Diese Seite ist dort Ausgangspunkt der Live-Demo und des Arbeitsauftrags. | `~/Projekte/ausbildungskraefte-deutsch/` |

Im Projekt `ausbildungskraefte-deutsch` liegen zwei Dinge, die dieses Repo betreffen:

- **Fachliche Prüfung von Beispiel 16** „Argumentations-Trainer" mit sechs Befunden, dazu der fachdidaktische Hintergrund und die fertige Ersatzzeile: `erprobung/hintergrund/beispiel-16-pruefung.md`, `beispiel-16-ersatzzeile.txt`, `argumentieren-fachdidaktik.md`.
- **Demo-Ablauf**, der zeigt, wie die Seite in der Veranstaltung benutzt wird: `demo/demo-ablauf.md`, dazu `demo/eingabe-demo.txt`.

## Quellen, die die Seite selbst verlinkt

Im Abschnitt „Quellen und weiterführende Materialien" der `index.html`, dort direkt nachzulesen: AIS.chat-Selbstlernkurs im HLA-Moodle, KIMADU NRW, Goethe-Institut (Prompting-Handreichung 2025), KI-Schulpreis 2025, KI in Grund- und Förderschule Hessen (Edumaps), KI-Campus, Prompting-Kompetenz NRW. Im Kopfbereich zusätzlich der Selbstlernkurs und die AIS.chat-Fortbildungen im Schulportal.

## Was hier nicht liegt

- Fertige dienstliche Endprodukte (PDFs, Handzettel) zu dieser Seite: keine bekannt. Entstünden welche, gehören sie nach `~/Documents/Arbeit/F3-4/`, nicht ins Repo.
- Kurzlink-Verwaltung: Ziel- und Deaktivierungslinks der t1p-Kurzlinks liegen in `~/Documents/Arbeit/MediaLab/AIS.chat/t1p-Kurzlinks/`, nicht im Repo.
