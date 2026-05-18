# ais-chat-deutsch-ideen

Interaktive Sammlung mit 42 Praxisbeispielen für den Einsatz von KI (AIS.chat) im Deutsch-Unterricht – Primarstufe bis Sekundarstufe II.

## Was ist das?

Eine einzelne HTML-Seite mit filterbaren Good-Practice-Beispielen für den KI-Chatbot **AIS.chat** im Fach Deutsch. Gedacht als Inspirationsquelle für Lehrkräfte und Deutsch-Ausbilder in Hessen.

Die Beispiele decken fünf AIS.chat-Konfigurationsebenen ab:

- **Prompts** – direkte Eingaben zur Unterrichtsvorbereitung
- **Assistenten** – konfigurierte KI-Helfer mit Fachwissen
- **Lernszenarien** – aufgabenbasierte Settings für Schülerinnen und Schüler
- **Dialogpartner** – virtuelle Figuren mit eigenem Charakter
- **Bildgenerierung** – KI-erzeugte Bilder als Unterrichtsmaterial

12 der 42 Beispiele tragen zusätzlich das Querschnittsetikett **Inklusion / Differenzierung / DaZ** und enthalten konkrete Differenzierungshinweise für verschiedene Förderschwerpunkte und Sprachniveaus.

## Live ansehen

👉 <https://mgkurz.github.io/ais-chat-deutsch-ideen/>

## Funktionen

- Filter nach Schulstufe (Primarstufe, Sek I, Sek II)
- Filter nach AIS.chat-Ebene (Prompt, Assistent, Lernszenario, Dialogpartner, Bildgenerierung)
- Filter nach Thema (Inklusion / DaZ)
- Alle Filter kombinierbar, beim Start alles sichtbar
- Accordion-Karten, mehrere gleichzeitig öffenbar
- Erklärung der AIS.chat-Ebenen im Kopfbereich
- Quellenverzeichnis mit Links zu KIMADU NRW, Goethe-Institut, KI-Campus u.a.

## Technik

- Eine einzige `index.html` – kein Framework, kein Build-Step
- Alle 42 Einträge als JS-Datenarray in der Datei
- Responsive (iPad + Laptop), touch-optimiert
- Datenschutzerklärung integriert (Hash-Routing, keine zweite Datei)
- Keine externen Abhängigkeiten – keine Cookies, kein Tracking, keine CDN-Schriften
- DSGVO-konform

## Deployment

Datei `index.html` ins Repo legen, GitHub Pages auf den `main`-Branch zeigen lassen. Fertig.

## Weiterverwendung

Die Datenstruktur ist erweiterbar. Weitere Fächer oder Beispiele können direkt im `DATA`-Array in der `index.html` ergänzt werden. Jeder Eintrag hat die Felder: `id`, `title`, `category`, `level`, `aisType`, `aisTypeLabel`, `shortDesc`, `content` und optional `inklusion`.

## Lizenz

CC BY-SA 4.0 · Hessische Lehrkräfteakademie · Martin Kurz

## Kontakt

Martin Kurz, Hessische Lehrkräfteakademie, Dezernat II.3 Medien (Medialab)
E-Mail: <martin.kurz@bildung.hessen.de>
