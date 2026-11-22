# Musik-Apps

Minimalistische Übersichtsseite für Musikunterricht-Web-Apps: große,
anklickbare Karten (Screenshot + Titel), die direkt zur jeweiligen App führen,
gegliedert in zwei Kategorien.

**Übungs-Apps** (jeweils eigenes Repo):

- [Rhythmus-Generator](https://github.com/mitlaeuferfotografie/Rhythmus-Generator) -
  freies Bau-Werkzeug für eigene Rhythmen, ohne Bewertung.
- [Rhythmus-Trainer](https://github.com/mitlaeuferfotografie/Rhythmus-Trainer) -
  Hör-Übungsspiel mit Punkten und Levels.
- [Noten-Rätsel](https://github.com/mitlaeuferfotografie/Noten-Raetsel) -
  Wissensquiz zu Notenwerten mit sechs Spielformaten.

**Vertonungen** (stumme Filme, zu denen die Kinder selbst Musik machen -
liegen direkt in diesem Repo als Unterordner):

- [Die Lorenfahrt](https://mitlaeuferfotografie.github.io/Musik-Apps/lorenfahrt/)
  (`lorenfahrt/`) - animierte Fahrt mit einer Lore durch einen dunklen
  Stollen, 7 Szenen, gut eine Minute, umschaltbar zwischen Seitenansicht und
  Mitfahrt (Ego-Perspektive). Eingebauter QR-Code (Knopf "QR-Code" bzw.
  Taste Q) zum Öffnen auf Tablets. Schriften liegen lokal in
  `lorenfahrt/fonts/` (kein Google-Fonts-Abruf, DSGVO). Dunkles Design
  bewusst als Ausnahme von der hellen Palette: Es ist ein Film im Stollen.
  Entstanden für die Reihe "Ritter Rost macht Urlaub" (Stunde 3), eigene
  Gestaltung ohne Figuren/Bilder aus dem Buch.

Eine neue Vertonung kommt als eigener Unterordner hierher (mit Zurück-Link
und Impressum-Link wie unten beschrieben) und bekommt eine Karte im Abschnitt
"Vertonungen" in `index.html`.

Reines Vanilla HTML/CSS, kein Build-Schritt, kein Framework - passt sich
responsiv jeder Bildschirmgröße an (eine Spalte auf schmalen Bildschirmen,
mehrere Spalten ab ca. 600px). Bewusst KEIN automatischer Hell-/Dunkelmodus
mehr (anders als die ursprüngliche Fassung) - dieselbe helle Slate-/Amber-
Palette + royalblaue Kopfleiste wie die drei verlinkten Apps selbst, damit
der Übergang von der Übersicht in eine App sich nahtlos anfühlt (siehe
`:root`-Variablen in style.css, identisch zu denen der drei App-Repos).

Die Screenshots in `assets/` sind reale, per Headless-Chrome erzeugte
Aufnahmen der jeweiligen LIVE-App (Stand: 2026-09-24; `lorenfahrt.png`: 2026-11-22) - bei größeren
optischen Änderungen an einer der drei Apps sollten sie aktualisiert
werden (Befehl siehe Git-Historie dieser Datei/`CLAUDE.md`).

## Lokal starten

```bash
node serve.js
```

und dann `http://localhost:5180` öffnen - oder `index.html` direkt per
Doppelklick im Browser öffnen.

## Hosting über GitHub Pages

- Repository: https://github.com/mitlaeuferfotografie/Musik-Apps
- Live-URL: https://mitlaeuferfotografie.github.io/Musik-Apps/

## Impressum &amp; Datenschutz (verbindliche Konvention)

`impressum.html` in diesem Repo ist die EINE zentrale Impressum-/
Datenschutz-Seite für alle Musik-Apps - Adresse/E-Mail werden nur hier
gepflegt. Kein anderes Repo dupliziert den Text; alle anderen Apps
verlinken nur per absoluter URL:
`https://mitlaeuferfotografie.github.io/Musik-Apps/impressum.html`

Für jede App (auch jede zukünftige) gilt die Zwei-Klick-Regel - von jedem
Zustand der App aus in maximal zwei Klicks erreichbar, klar mit
"Impressum" beschriftet (kein reines Icon):

- **App mit Einstellungsmenü (⚙):** "Impressum" als eigener, klar
  beschrifteter Link/Menüpunkt am Ende des Einstellungen-Flyouts (Klasse
  `.settings-legal-link` - siehe Rhythmus-Generator/-Trainer/Noten-Rätsel
  als Vorlage). NICHT als zusätzlicher Footer-Link auf der Spielfläche.
  Voraussetzung: Das Einstellungsmenü selbst muss aus JEDEM Bildschirm der
  App heraus erreichbar sein (auch mitten in einer laufenden Übung/Runde,
  nicht nur auf dem Startbildschirm) - das im Zweifel vor dem Ergänzen des
  Impressum-Links einmal explizit prüfen.
- **App ohne Einstellungsmenü** (z. B. diese Übersichtsseite): kleiner,
  unauffälliger Footer-Link ("Impressum", kleine Schrift, gedeckte Farbe)
  unten auf der Seite.

Neue Apps bekommen diesen Menüpunkt von Anfang an, ohne dass es jedes Mal
extra erwähnt werden muss.

## Zurück-Link zur Übersicht (verbindliche Konvention)

Jede der drei Apps hat oben RECHTS in der Toolbar einen dauerhaft
sichtbaren Link zurück zu dieser Übersichtsseite: Pfeil (←) mit
"Musik-Apps" klein darunter, Klasse `.toolbar-home-link`
(`margin-left: auto`, damit er sich unabhängig vom Rest des Toolbar-
Inhalts an den rechten Rand schiebt). Bewusst RECHTS statt links: links
sitzen in mehreren Apps bereits In-App-"Zurück"-Knöpfe (z. B. "Level
wählen", "Zurück" zwischen Hub/Format), ein zweiter Zurück-Pfeil an
derselben Stelle hätte Kinder verwirrt.

```html
<a class="toolbar-home-link" href="https://mitlaeuferfotografie.github.io/Musik-Apps/" title="Zurück zur Musik-Apps-Übersicht">
  <span class="toolbar-home-arrow">←</span>
  <span class="toolbar-home-label">Musik-Apps</span>
</a>
```

Neue Apps übernehmen dieses Snippet (samt `.toolbar-home-link`-CSS aus
einer der drei bestehenden Apps) als letztes Kind der Toolbar, ohne dass
es jedes Mal extra erwähnt werden muss.

## Icon je App (verbindliche Konvention)

Jede App hat ein eigenes Emoji-Icon, das an ZWEI Stellen identisch
erscheint: im eigenen `<h1>`-Header der App UND vor dem Titel auf der
jeweiligen Karte hier in der Übersicht (`.card-title`) - so erkennen auch
Kinder, die noch nicht lesen können, welche App gemeint ist.

- 🎼 Musik-Apps (diese Übersichtsseite, Notenschlüssel)
- 🎵 Rhythmus-Generator (Note)
- 👂 Rhythmus-Trainer (Ohr, für die Hör-Übung)
- ❓ Noten-Rätsel (Fragezeichen, für das Quiz)
- ⛏️ Die Lorenfahrt (Spitzhacke, Bergwerk)

Eine neue App bekommt beim Anlegen ebenfalls ein eigenes, thematisch
passendes Icon nach diesem Muster - an beiden Stellen gleichzeitig
ergänzen.
