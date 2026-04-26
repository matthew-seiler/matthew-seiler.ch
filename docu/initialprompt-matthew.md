# Initial-Prompt für Claude Code in VS Code

Diesen Text kopiert Matthew (gemeinsam mit Patric) in Claude Code im VS Code.
Claude Code liest automatisch die CLAUDE.md im Repo und kennt dann den Projektkontext.

---

## Prompt-Text (kopieren und in Claude Code einfügen)

```
Hallo Claude,

ich bin Matthew, 13 Jahre, und mein Vater Patric sitzt neben mir. Wir bauen
zusammen meine erste Homepage: matthew-seiler.ch

Was bereits steht:
- Das GitHub-Repo matthew-seiler/matthew-seiler.ch existiert und ist gepusht.
- Die Seite ist live unter https://matthew-seiler.ch (aktuell nur Hallo Welt).
- Im Repo liegt eine CLAUDE.md mit dem ganzen Projektkontext – bitte lies sie zuerst.
- Im images-Ordner liegen zwei KI-generierte Hintergrundbilder:
  bg-landing.jpg (für die Hauptseite) und bg-blog.jpg (für die Blogseite).

Was ich bauen will:

1. HAUPTSEITE (index.html): Ein Dashboard mit meinem Namen als Titel
   ("Matthew Seiler") und dem Untertitel "Mein Blog". Darunter ein Grid
   mit grafischen Tiles für meine Blogposts. Zunächst nur ein Tile.
   Das Tile soll richtig cool aussehen: halbtransparenter Hover-Effekt mit
   Glow, das Bild zoomt leicht beim Hover, und das Ganze hebt sich an.
   Das Hintergrundbild bg-landing.jpg soll den gesamten Hintergrund füllen.

2. BLOG-DETAILSEITE (blog/universum.html): Wenn man auf das Tile klickt,
   öffnet sich mein Blogpost. Die Seite soll wie ein Schreibblatt aussehen –
   weisses Papier im Hochformat, das über dem Hintergrundbild bg-blog.jpg
   schwebt. Mit einer coolen Einfahrt-Animation. Oben ein Zurück-Button.
   Der Text hat einen Titel, darunter "Von Matthew Seiler" als Autorenzeile
   und das Datum. Am Ende des Textes kommt ein Abschnitt "Quellenangaben"
   (da schreibe ich später die Quellen rein, mach erstmal einen Platzhalter
   mit "TODO: Quellen werden ergänzt").

3. Mein erster Blogpost heisst "Die unglaublichsten Objekte im Universum"
   und handelt von Dronensternen, schwarzen Löchern, Wurmlöchern und anderen
   verrückten Dingen im Weltraum. Den Text gebe ich dir gleich separat.

Wichtig:
- Kein Bootstrap, kein Tailwind, kein jQuery. Nur HTML, CSS und etwas JS.
- Erkläre mir kurz was du machst, bevor du es tust.
- Mach einen sauberen Commit und push, wenn alles fertig ist.
- Danach sage mir den Befehl für den Deploy auf den VPS.

Fang an, indem du die CLAUDE.md liest und mir sagst, was du als Erstes tun
wirst. Dann legen wir los!
```

---

## Hinweise für Patric

Vor dem Prompt vorbereiten:
1. CLAUDE.md muss im Repo-Hauptverzeichnis liegen (neben der index.html).
2. Die beiden Hintergrundbilder (bg-landing.jpg und bg-blog.jpg) müssen im
   images/-Ordner liegen.
3. Matthews Blogtext (~500 Wörter) sollte als Textdatei bereitliegen, damit
   Matthew ihn Claude Code geben kann, wenn Claude danach fragt.

Nach dem ersten Prompt:
- Claude Code wird die CLAUDE.md lesen und dann Schritt für Schritt die
  Dateien erstellen (index.html, css/style.css, blog/universum.html).
- Matthew gibt zwischendurch seinen Blogtext ein.
- Am Ende macht Claude Code einen Commit und Push.
- Matthew deployed dann selbst mit:
  ssh matth@langsamer "cd /var/www/matthew-seiler && git pull"
- Dann Browser öffnen und staunen.

Erfolgsmarker:
- matthew-seiler.ch zeigt das Dashboard mit dem Weltraum-Hintergrund.
- Das Tile sieht cool aus mit Hover-Effekt.
- Klick auf das Tile öffnet den Blogpost im Schreibblatt-Look.
- Matthew kann erklären, was in jeder Datei steht.
