# CLAUDE.md – Projektkontext matthew-seiler.ch

## Wer arbeitet hier

Matthew Seiler, 13 Jahre alt, baut seine erste persönliche Homepage. Er ist Programmier-Anfänger. Sein Vater Patric (CEO ITConsulting24 AG) hat die gesamte Infrastruktur vorbereitet und beobachtet über TeamViewer. Matthew tippt selbst und lernt dabei. Kommunikation ist auf Deutsch, Code und Kommentare auf Englisch.

## Umgangsregeln

- Matthew ist 13 und Anfänger. Kein Belehren, keine Überforderung.
- Immer nur ein Schritt auf einmal. Warte auf Rückmeldung bevor du weitergehst.
- Fehler sind erlaubt und erwünscht – sie sind Lernmomente.
- Erkläre kurz was du tust und warum, aber halte es einfach.
- Sichtbarer Text auf der Website ist Deutsch.
- Code, Kommentare, Dateinamen, CSS-Klassen und Commit-Messages sind auf Englisch.
- HTML-Einrückung: 2 Spaces.

## Technische Regeln (Phase 1)

- Keine externen Frameworks: kein Bootstrap, kein Tailwind, kein jQuery. Nur reines HTML, CSS und etwas JavaScript.
- Pro Git-Commit eine einzige logische Änderung mit beschreibender englischer Commit-Message.
- Keine SSH-Keys, Passwörter oder Tokens ins Repo committen. Niemals.

## Lokale Umgebung (SCB, Windows 11 Pro)

- Windows-Profil: matth_29mawpl
- Editor: VS Code mit Claude Code Extension
- Git + GitHub CLI (gh), authentifiziert als GitHub-User: matthew-seiler
- Python 3.12 via UV, Git-Bash verfügbar
- Arbeitsverzeichnis: C:\Users\matth_29mawpl\projekte\matthew-seiler.ch\
- GitHub-Repo: https://github.com/matthew-seiler/matthew-seiler.ch (public)

## Hosting (Infomaniak VPS, Rocky Linux 9)

- IP: 83.228.207.39, SSH-Alias auf SCB: langsamer
- Webserver: Apache 2.4, eigener vHost matthew-seiler.ch.conf
- DocumentRoot: /var/www/matthew-seiler/ (Owner matth:apache)
- HTTPS via Let's Encrypt mit Auto-Renewal
- Matthews Linux-User: matth (UID 1001, keine sudo-Rechte, Key-only SSH)
- SSH-Key auf SCB: C:\Users\matth_29mawpl\.ssh\id_ed25519 (keine Passphrase)

## Deploy-Workflow (bewusst manuell)

```bash
# 1. Lokal in VS Code editieren
# 2. Committen und pushen
git add .
git commit -m "Beschreibung der Änderung"
git push

# 3. Auf den VPS deployen
ssh matth@langsamer "cd /var/www/matthew-seiler && git pull"

# 4. Browser öffnen: https://matthew-seiler.ch
```

## Was auf dem VPS sonst noch läuft

apartments-capricorn.com läuft auf dem gleichen VPS, ist aber komplett entkoppelt. Matthew hat darauf keinen Zugriff und soll das auch nicht anfassen.

## Aktuelles Vorhaben (April 2026)

Matthews Homepage ist eine persönliche Seite mit Blog-Funktion. Zweistufige Navigation: Dashboard → Detailseite.

### Hauptseite (Landingpage / Dashboard)
- Eigenes KI-generiertes Weltraum-Hintergrundbild (bg-landing.jpg), fixed
- Grosser Titel "Matthew Seiler" mit Untertitel "Mein Blog"
- Scrollbares Grid mit grafischen Tiles für Blogposts
- Zunächst nur 1 Tile (erster Blogpost über das Universum)
- Tiles haben halbtransparenten Hover-Effekt mit Glow und leichtem Anheben
- Hintergrundbild im Tile zoomt beim Hover sanft rein
- Klick auf ein Tile öffnet die Detailseite

### Blog-Detailseite (Schreibblatt)
- Eigenes KI-generiertes Hintergrundbild (bg-blog.jpg), fixed
- Zurück-Button zum Dashboard
- Der Blogtext erscheint in einem weissen "Schreibblatt" (Paper-Look) im Hochformat
- Das Schreibblatt schwebt über dem Hintergrundbild
- Einfahrt-Animation beim Laden (von unten, mit Scale und Fade)
- Blocksatz, schöne Typografie (Serif-Schrift für den Text)
- Autorenzeile unter dem Titel (z.B. "Von Matthew Seiler")
- Am Ende des Textes: Quellenangaben-Abschnitt (kann zunächst als TODO-Platzhalter stehen, bis die Quellen bekannt sind)

### Erster Blogpost
- Thema: Dronensterne, schwarze Löcher, Wurmlöcher und die ungewöhnlichsten Objekte des Universums
- Text hat ca. 500 Wörter, von Matthew selbst geschrieben

## Dateistruktur

```
matthew-seiler.ch/
  index.html              <- Landingpage mit Dashboard
  css/
    style.css             <- Einziges Stylesheet
  blog/
    universum.html        <- Erster Blogpost (Schreibblatt)
  images/
    bg-landing.jpg        <- Hintergrundbild Landingpage (KI-generiert)
    bg-blog.jpg           <- Hintergrundbild Blog-Detail (KI-generiert)
    tile-universum.jpg    <- Vorschaubild für den Blog-Tile (optional)
  CLAUDE.md               <- Diese Datei (nicht auf der Website sichtbar)
```

## Spätere Phasen (noch nicht anfangen)

- Phase 2: Flask-Backend mit UV/Python
- Automatischer Webhook-Deploy statt manuelles git pull
- Weitere Blogposts und Tile-Kategorien
