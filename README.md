# Penny – private Finance PWA

## GitHub Pages veröffentlichen

1. Neues **öffentliches** GitHub-Repository erstellen, z. B. `penny-app`.
2. **Inhalt** des Ordners `Penny-PWA` (nicht den Ordner selbst) ins Stammverzeichnis des Repositorys hochladen: `index.html`, `styles.css`, `app.js`, `sw.js`, `manifest.webmanifest` und `icons/`.
3. Unter **Settings → Pages → Build and deployment** die Option **Deploy from a branch**, Branch `main`, Ordner `/(root)` auswählen und speichern.
4. Nach der Bereitstellung `https://DEIN-NAME.github.io/penny-app/` auf dem iPhone in Safari öffnen.
5. Safari → Teilen → **Zum Home-Bildschirm** → Hinzufügen.
6. App einmal online vollständig öffnen, damit die Dateien für den Offlinebetrieb zwischengespeichert werden.

## Datenschutz

Die App verwendet IndexedDB im Browser für Buchungen, Kategorien, wiederkehrende Regeln und Belegbilder. Es gibt keinen Server für Finanzdaten, keine Tracker, keine externe API und keine Bibliotheken von Drittanbietern. GitHub kann technische Zugriffsdaten beim Ausliefern der App erfassen. Der Repository-Inhalt ist öffentlich, also **niemals persönliche Buchungen in den Quellcode oder das Repository hochladen**.

**Wichtig:** Lokale Webdaten können beim Löschen von Website-Daten, Browser-Reset oder Gerätewechsel verloren gehen. Unter Mehr → Backup erstellen regelmäßig eine JSON-Sicherung erstellen und sicher verwahren. Diese Datei enthält unverschlüsselte persönliche Daten und ggf. Belegfotos. Die App bietet keine biometrische Zugriffssperre und keine Synchronisierung zwischen Geräten.

## Funktionsweise und Grenzen

- Einnahmen und Ausgaben, Editieren/Löschen, Kategorien, Suche und Monatsfilter
- Lokale Datenspeicherung, offlinefähige App-Shell nach erstem Onlinebesuch
- Monatsübersicht, Ausgabenkategorien, Prognose, Trends, Kalender und Insights
- Wiederkehrende Buchungen werden beim Öffnen der App nachgetragen (nicht im Hintergrund)
- Belegfotos werden lokal gespeichert, keine automatische Texterkennung/OCR
- Geteilte Ausgaben zeigen den Pro-Kopf-Anteil, buchen aber den Gesamtbetrag
- CSV-Import erwartet die Spalten `Datum;Typ;Betrag;Beschreibung;Kategorie;Notiz`, wobei Typ `income` oder `expense` ist und Datum `YYYY-MM-DD`.
- JSON-Backup und -Wiederherstellung (mit Belegen)
- Keine iCloud-Synchronisierung, keine Face-ID-Sperre, keine Siri-Integration und keine nativen Widgets

## Testhinweis

Die JavaScript-Dateien wurden auf Syntax geprüft; ein vollständiger Test auf einem echten iPhone ist hier nicht möglich. Vor produktiver Verwendung mit Testbuchungen Import, Export und Offlinebetrieb prüfen.

## Update 1.1
- iOS: kein automatischer Zoom beim Fokussieren von Eingabefeldern; Pinch-Zoom in der Web-App deaktiviert.
- Alle Kategorien (einschließlich Standardkategorien) lassen sich umbenennen, umfärben, mit Symbol versehen und löschen.
- Beim Umbenennen werden vorhandene Buchungen und wiederkehrende Regeln aktualisiert.
- Kategorien, die noch in Buchungen oder wiederkehrenden Regeln verwendet werden, müssen vor dem Löschen dort neu zugewiesen werden.
- Nach dem Löschen aller Kategorien werden Standardkategorien nicht erneut angelegt.
- Aktualisiere alle Dateien auf GitHub Pages; bestehende lokale Buchungen bleiben bei gleicher Website-Adresse erhalten.
