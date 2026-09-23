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
responsiv jeder Bildschirmgröße an (ein Spalte auf schmalen Bildschirmen,
zwei Spalten ab ca. 600px) und unterstützt automatisch Hell-/Dunkelmodus
(`prefers-color-scheme`).

Die Screenshots in `assets/` sind reale, per Headless-Chrome erzeugte
Aufnahmen der jeweiligen App (Stand: 2026-09-23) - bei größeren optischen
Änderungen an einer der drei Apps sollten sie aktualisiert werden.

## Lokal starten

```bash
node serve.js
```

und dann `http://localhost:5180` öffnen - oder `index.html` direkt per
Doppelklick im Browser öffnen.

## Hosting über GitHub Pages

- Repository: https://github.com/mitlaeuferfotografie/Musik-Apps
- Live-URL: https://mitlaeuferfotografie.github.io/Musik-Apps/
