# matthew-seiler.ch

Meine persönliche Homepage mit Blog. Gebaut mit reinem HTML, CSS und JavaScript.

## Website aktualisieren

### Schritt 1: Änderungen lokal machen

Dateien in VS Code bearbeiten. Mit Live Server (`Go Live` unten rechts) die Vorschau im Browser prüfen.

### Schritt 2: Änderungen committen und pushen

```bash
git add .
git commit -m "Kurze Beschreibung was geändert wurde"
git push
```

Pro Commit nur eine logische Änderung. Commit-Message auf Englisch.

### Schritt 3: Website live schalten

```bash
ssh matth@langsamer "cd /var/www/matthew-seiler && git pull"
```

### Schritt 4: Prüfen

Im Browser öffnen: [https://matthew-seiler.ch](https://matthew-seiler.ch)

## Dateistruktur

```
matthew-seiler.ch/
  index.html            ← Hauptseite (Dashboard mit Blog-Tiles)
  css/
    style.css           ← Einziges Stylesheet
  blog/
    universum.html      ← Erster Blogpost
  images/
    bg-landing.jpg      ← Hintergrundbild Hauptseite
    bg-blog.jpg         ← Hintergrundbild Blogseite
  CLAUDE.md             ← Projektkontext für Claude Code
  README.md             ← Diese Datei
```

## Technische Regeln

- Kein Bootstrap, Tailwind oder jQuery – nur HTML, CSS und etwas JS
- HTML-Einrückung: 2 Spaces
- Sichtbarer Text: Deutsch
- Code, Dateinamen, Commits: Englisch
- Keine Passwörter oder Keys ins Repo
