# Musik-Apps

Minimalistische Übersichtsseite für drei Musikunterricht-Web-Apps: große,
anklickbare Karten (Screenshot + Titel), die direkt zur jeweiligen App führen.

- [Rhythmus-Generator](https://github.com/mitlaeuferfotografie/Rhythmus-Generator) -
  freies Bau-Werkzeug für eigene Rhythmen, ohne Bewertung.
- [Rhythmus-Trainer](https://github.com/mitlaeuferfotografie/Rhythmus-Trainer) -
  Hör-Übungsspiel mit Punkten und Levels.
- [Noten-Rätsel](https://github.com/mitlaeuferfotografie/Noten-Raetsel) -
  Wissensquiz zu Notenwerten mit sechs Spielformaten.

Reines Vanilla HTML/CSS, kein Build-Schritt, kein Framework - passt sich
responsiv jeder Bildschirmgröße an (eine Spalte auf schmalen Bildschirmen,
mehrere Spalten ab ca. 600px). Bewusst KEIN automatischer Hell-/Dunkelmodus
mehr (anders als die ursprüngliche Fassung) - dieselbe helle Slate-/Amber-
Palette + royalblaue Kopfleiste wie die drei verlinkten Apps selbst, damit
der Übergang von der Übersicht in eine App sich nahtlos anfühlt (siehe
`:root`-Variablen in style.css, identisch zu denen der drei App-Repos).

Die Screenshots in `assets/` sind reale, per Headless-Chrome erzeugte
Aufnahmen der jeweiligen LIVE-App (Stand: 2026-09-24) - bei größeren
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
