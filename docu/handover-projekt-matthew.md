# Projekt Matthew – Handover für Claude

Dieses Dokument fasst den Kontext zusammen, damit du sofort hilfreich mitarbeiten kannst, sobald ein neuer Chat im Projekt „Matthew" startet.

## Wer ist Matthew

Matthew Seiler ist 13 Jahre alt und lernt gerade das Programmieren. Er arbeitet auf einem Windows-11-PC (Hostname: SCB, Benutzerprofil: matth_29mawpl), nutzt VS Code und Claude Code als Entwicklungsumgebung. Sein GitHub-Handle ist matthew-seiler, seine E-Mail ist matthew.seiler@itconsulting24.com.

Sein Vater Patric (GitHub: patricseiler) ist Admin und CEO von ITConsulting24 AG. Patric hat die gesamte Infrastruktur für Matthew vorbereitet und begleitet ihn beim Einstieg. Claude-Zugang läuft über Patrics Max-Plan-Abo.

Wichtig für den Umgangston: Matthew ist ein Anfänger. Nicht belehrend, nicht überfordernd. Begriffe werden bei erster Nennung kurz erklärt. Immer nur ein Schritt auf einmal.

## Infrastruktur (steht bereits)

Lokal auf SCB: VS Code mit Claude Code Extension, Git, GitHub CLI (als matthew-seiler authentifiziert), Python 3.12 via UV, Git-Bash. Arbeitsverzeichnis: C:\Users\matth_29mawpl\projekte\matthew-seiler.ch\. GitHub-Repo: matthew-seiler/matthew-seiler.ch (public).

Hosting: Infomaniak VPS (Rocky Linux 9, IP 83.228.207.39, SSH-Alias "langsamer"). Apache 2.4, eigener vHost, DocumentRoot /var/www/matthew-seiler/. HTTPS via Let's Encrypt. Matthews Linux-User matth hat keine sudo-Rechte und nur Key-based SSH-Zugang.

Deploy-Workflow: lokal editieren → git push → ssh matth@langsamer "cd /var/www/matthew-seiler && git pull". Bewusst manuell, damit Matthew den Ablauf versteht.

Auf dem gleichen VPS läuft apartments-capricorn.com komplett entkoppelt – nicht anfassen.

## Aktueller Stand (April 2026)

Die Seite matthew-seiler.ch ist live mit einem Initial Commit (Hello World). Das GitHub-Repo existiert und der VPS klont davon.

## Was gebaut wird

Eine persönliche Homepage mit Blog-Funktion. Zweistufige Navigation:

Hauptseite (Dashboard): Scrollbares Grid mit grafischen Tiles für Blogposts. Weltraum-Hintergrundbild (KI-generiert). Tiles mit halbtransparentem Hover-Effekt, Glow und Zoom. Klick öffnet die Detailseite.

Blog-Detailseite (Schreibblatt): Eigenes Hintergrundbild (KI-generiert). Weisses Papier-Element im Hochformat, schwebt über dem Hintergrund. Autorenzeile, Blocksatz, schöne Serif-Typografie, Quellenangaben am Ende. Einfahrt-Animation beim Laden.

Erster Blogpost: Dronensterne, schwarze Löcher, Wurmlöcher und die ungewöhnlichsten Objekte des Universums (~500 Wörter, von Matthew geschrieben).

Technische Regeln: Reines HTML/CSS/JS, keine Frameworks. HTML-Indent 2 Spaces. Sichtbarer Text Deutsch, Code Englisch. Pro Commit eine logische Änderung.

## Spätere Phasen

Phase 2 ist ein Flask-Backend mit UV/Python. Kommt erst wenn Phase 1 solide läuft.
