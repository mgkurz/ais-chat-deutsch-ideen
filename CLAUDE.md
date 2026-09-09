# CLAUDE.md

Diese Datei gibt Claude Code den Kontext und die Regeln für dieses Projekt.
Claude Code liest sie zu Beginn jeder Session automatisch.
Kommunikation, Arbeitsweise und Kenntnisstand stehen global in `~/.claude/CLAUDE.md`.

## Autor und Verantwortung

- **Autor**: Martin Kurz
- **Institution**: Hessische Lehrkräfteakademie (HLA), Dezernat II.3 Medien
- **Rolle**: Beauftragt für die Produktion von Bildungsmedien in der Lehrkräftebildung, sekundär Unterrichtsmaterialien im Kontext der Lehrkräftefortbildung
- **Kontaktdaten** (dienstliche E-Mail, GitHub): nicht im öffentlichen Repo. Sie stehen lokal in `CLAUDE.local.md` (ge-gitignored) und im Impressum des jeweiligen Artefakts.
- Die Verantwortung als Autor wird wahrgenommen, auch im Datenschutz. Transparenz ist wichtig.
- Hinweis zum Status: privat erstellt mit dienstlichem Bezug, ohne formale Anbindung an einen Datenschutzbeauftragten der HLA. Die Verantwortung liegt beim Autor.
- Jede Veröffentlichung braucht Impressum, Datenschutzerklärung und Nutzungsbedingungen.

## Projektkontext

- **Was**: Interaktive Sammlung mit 42 Praxisbeispielen für den Einsatz von AIS.chat im Deutschunterricht, Primarstufe bis Sekundarstufe II. Eine einzelne `index.html` mit filterbaren Beispielkarten, Kopier-Schaltfläche je Beispiel sowie integriertem Impressum und integrierter Datenschutzerklärung (Hash-Routing `#impressum` / `#datenschutz`, keine zweite Datei).
- **Zielgruppe**: Deutsch-Lehrkräfte und Ausbildungskräfte Deutsch in Hessen.
- **Einsatzkontext**: GitHub Pages unter `mgkurz.github.io/ais-chat-deutsch-ideen`, Kurzlink `t1p.de/ais-chat-deutsch`. Direkter Ausgangspunkt der Live-Demo beim Forum der Ausbildungskräfte Deutsch am 10.09.2026.
- **Status**: bestehendes, veröffentlichtes Artefakt, kein Neubau. Jede Änderung ist Pflege an einer laufenden, verlinkten Seite.

## Ablage und Orte

- Dieses Projekt ist Produktionsort und Quelle der Wahrheit für Quellen und Doku (HTML, MD, Skripte, aggregierte Zahlen).
- Fertige dienstliche Endprodukte (PDFs etc.) liegen nicht im Repo und nicht auf GitHub, sondern lokal in `~/Documents/Arbeit/F3-4/` (je Thema ein Ordner). Das Repo hält die reproduzierbaren Quellen, `ORTE.md` verweist auf den Ablageort. Teamordner und Mail erhalten nur Kopien.
- Externe Fundorte in einer `ORTE.md` verweisen statt kopieren. Projektstand optional in `STATUS.md`.
- Privates GitHub-Remote ist Standard, Push gehört zum Arbeitsabschluss. Öffentlich nur bewusst, dann gilt die Repo-Mail-Regel aus der globalen CLAUDE.md.

## Lizenz

- Standard für Artefakte (einzelne HTML-Dateien, ggf. mit Bildern): alles unter CC BY-SA 4.0, auch der eingebettete HTML/CSS/JS-Code. Kein getrenntes MIT.
- MIT (oder andere freie Code-Lizenz) nur bei echtem, eigenständigem Programm: App, wiederverwendbares Tool, Komponentenbibliothek.
- Kontextabhängig. Im Zweifel kurz nachfragen.

**Für dieses Projekt gilt der Standardfall: CC BY-SA 4.0, auch für den eingebetteten Code der `index.html`. Kein MIT.** Die Lizenz steht an drei Stellen und muss dort konsistent bleiben: in `LICENSE`, im Footer der Seite und im Abschnitt „Lizenz" des Impressums.

## Tech-Stack und Veröffentlichung

- HTML5, CSS3, Vanilla JavaScript
- Veröffentlichung aktuell über GitHub Pages. Was dort technisch möglich ist, darf genutzt werden, besonders bei höherer Komplexität.
- Übergang zu React erst nach Rücksprache.
- Datenspeicherung bei Bedarf: Supabase (EU/Frankfurt). Noch keine Praxiserfahrung, daher die nötigen Schritte erklären, wenn es relevant wird.

**Konkret hier:**

- Eine einzige `index.html`. Kein Framework, kein Build-Step, keine externen Abhängigkeiten. CSS und JavaScript stehen inline in derselben Datei.
- Datenpflege ausschließlich im `DATA`-Array in der `index.html` (aktuell Zeilen 798 bis 841). Es gibt keine zweite Datenquelle, kein JSON, keine Datenbank.
- Feldstruktur eines Eintrags:

| Feld | Typ | Bedeutung |
| --- | --- | --- |
| `id` | Zahl | Fortlaufende Nummer, 1 bis 42. Eindeutig. |
| `title` | String | Titel der Karte. |
| `category` | String | Buchstabe A bis E und G. Historische Gliederung, wird von Rendering und Filter **nicht** ausgewertet. Beim Anlegen mitführen, nicht darauf verlassen. |
| `level` | Array | Eine oder mehrere Schulstufen: `"P"`, `"SI"`, `"SII"`. Steuert den Stufenfilter und die Stufen-Badges. |
| `aisType` | String | Technischer Schlüssel der AIS.chat-Funktion: `prompt`, `bildgenerierung`, `assistent`, `dialogpartner`, `lernszenario`. Steuert den Funktionsfilter und die Badge-Farbe. |
| `aisTypeLabel` | String | Sichtbare Beschriftung dazu. Muss zu `aisType` passen, siehe `TYPE_LABELS`. |
| `shortDesc` | String | Ein Satz, erscheint im geschlossenen Zustand der Karte und im Kopiertext. |
| `content` | String | HTML-Fragment mit den Inhaltsblöcken. Vorhandene Klassen: `block-prompt`, `block-lk` (Lehrkraft), `block-sus` (Schülerinnen und Schüler), `block-diff` (Differenzierung), je mit einem `span.block-label` als Überschrift. |
| `inklusion` | Boolean, optional | `true` setzt das Querschnittsetikett „Inklusion / DaZ" und schaltet den Themenfilter scharf. Aktuell bei 12 der 42 Einträge gesetzt. |

- Der Kopier-Button baut seinen Text aus `title`, `aisTypeLabel`, `level`, `shortDesc` und den Blöcken aus `content` (`buildCopyText()`). Nur Blöcke mit einer der vier oben genannten Klassen landen im Kopiertext. Wer eine neue Block-Klasse einführt, muss sie dort ergänzen, sonst fehlt der Block beim Kopieren.

## Beispiele pflegen

- **Ein Eintrag ist ein einzeiliges JS-Objektliteral.** Eine Zeile je Beispiel, kein Zeilenumbruch innerhalb eines Eintrags. Das ist Absicht: so bleibt jede Änderung ein Ein-Zeilen-Diff.
- **Vor jeder Änderung die Zeile als JavaScript gegenlesen.** Ein einziges unescaptes Zeichen bricht das gesamte `DATA`-Array, und dann bleibt die Seite komplett leer, nicht nur der eine Eintrag. Prüfung ohne Browser:

  ```sh
  node -e 'const DATA=[/* Zeile hier einsetzen */]; console.log("ok", DATA.length)'
  ```

  Oder das ganze Array aus der Datei schneiden und prüfen:

  ```sh
  sed -n '798,841p' index.html > /tmp/data-check.js && node --check /tmp/data-check.js && echo "Syntax ok"
  ```

- **Apostrophe im `content` müssen escaped werden** (`\'`), weil `content` in einfachen Anführungszeichen steht. Betrifft besonders die typografischen Zitatzeichen in Instruktionstexten: `‚Schuluniformen sollten Pflicht sein\'`. Deutsche Anführungszeichen `„ "` und doppelte `"` sind im einfach gequoteten String unproblematisch.
- **Nach jeder Änderung die Seite lokal öffnen und den geänderten Eintrag testen**: Karte aufklappen, Filter für seine Stufe und seine AIS.chat-Funktion setzen (er muss auftauchen und verschwinden), Kopier-Button drücken und den eingefügten Text lesen. Der Zähler oben muss weiter 42 von 42 melden.

  ```sh
  open index.html
  ```

- Ändert sich die Zahl der Beispiele, sind vier Stellen nachzuziehen: der `<title>`/`meta description`, die Unterzeile im Header, der Filterzähler („42 von 42 Beispielen", auch der `id="visibleCount"`) und der Satz zur Zahl der Inklusions-Beispiele in der Ebenen-Karte. Dazu die `README.md`.

## Datenschutz (DSGVO): nicht verhandelbar

- Keine externen CDNs, Analytics oder Tracker einbinden.
- Schriften lokal einbinden, notfalls mitliefern. Keine Remote-Fonts.
- Bilder, Medien und alle weiteren Assets lokal halten und mitliefern.
- Keine personenbezogenen Daten in Code, Kommentaren oder Commits, auch keine pseudonymisierten (IDs, Teilnehmerlisten, Exporte). Rohdaten nur in einer gitignorten Transitzone auswerten und löschen, committet werden nur Aggregate. Kolleginnen und Kollegen in Repo-Dateien nur mit Vornamen.
- Keine echten Schülerdaten in Beispielen. Immer Dummy-Daten.
- Bei jeder externen Abhängigkeit, die du vorschlagen willst: erst nennen und begründen, nicht ungefragt einbauen.

Die Seite erfüllt das heute vollständig: keine Cookies, kein Tracking, keine externen Ressourcen. Das ist in der eingebauten Datenschutzerklärung ausdrücklich zugesichert. Jede neue externe Ressource würde diese Zusicherung zur Falschaussage machen.

## Design

- Es gibt mehrere Design-Sets.
- Für AIS.chat liegt ein Styleguide als PDF vor, dazu Vorlagen-Dateien für Logo, Signets und Hintergründe.
- Assets werden lokal abgelegt oder diskret im Repo gehalten.
- **Dieses Projekt folgt keinem der Design-Sets im engeren Sinn.** Die Seite nutzt Systemschriften (`'Segoe UI', system-ui, -apple-system, sans-serif`) und eine eigene grüne Palette über CSS-Custom-Properties (`--color-accent: #4a7c59`, `--color-accent-dark: #2d5e3a`). Kein Barlow, keine AIS.chat-Farben Dark Purple und Mint, kein AIS.chat-Logo. Das ist kein Versehen, sondern der gewachsene Stand des Artefakts.
- **Ein Wechsel auf das AIS.chat-CD erfolgt nur nach Rücksprache.** Er betrifft Schrift, Farben, Badges und Kopfbereich, also die ganze Seite, und würde außerdem lokal mitgelieferte Schriftdateien nötig machen (keine Remote-Fonts, siehe Datenschutz). Also nie nebenbei, sondern als eigener, bewusst beauftragter Arbeitsschritt.

## Barrierefreiheit

- Semantisches HTML (heading-Hierarchie, button statt div mit onclick, alt-Texte).
- Ausreichende Farbkontraste, Tastaturbedienbarkeit.
- Grundlegende Konformität, kein WCAG-AAA-Aufwand.

## Code-Konventionen

- Kommentare und UI-Texte auf Deutsch.
- Kurze, lesbare Funktionen. Sprechende Namen.
- Lesbarkeit vor Performance. Performance ist hier zweitrangig.
- Keine vorzeitige Optimierung.

## Git

- Kurze, sinnvolle Commit-Messages auf Deutsch.
- `.env` und Konfigdateien mit Secrets gehören in `.gitignore`, niemals committen.
- Vor jedem Commit prüfen: keine personenbezogenen Daten, keine Keys.

**Repo-Mail hier:** Das Repo ist öffentlich, aber dienstlich verantwortet. Das Impressum nennt die Hessische Lehrkräfteakademie und die dienstliche Adresse. Deshalb bleibt es bei der global eingestellten dienstlichen Autor-Mail. Die private Adresse aus der globalen CLAUDE.md wird hier **nicht** gesetzt, weder global noch repo-lokal. Ihre Ausnahmeregel gilt nur für privat verantwortete Veröffentlichungen mit privatem Impressum, und dieses Repo ist keines. Die private Adresse steht bewusst nirgends in diesem Repo, auch nicht als Gegenbeispiel.
