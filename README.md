# MeinTag + GedankenBox — Version 1

## Enthalten
- Aufgaben erstellen, bearbeiten, löschen, abhaken, priorisieren und mit Fälligkeitsdatum versehen
- Tagesansicht und Fortschrittsbalken
- Notizen erstellen, bearbeiten, löschen; Volltextsuche über Notizen und Aufgaben
- Sprachnotizen aufnehmen, abspielen und löschen (IndexedDB)
- ZIP-Export und ZIP-Import inklusive Audioaufnahmen
- Hell-/Dunkelmodus, mobile Oberfläche, PWA-Manifest und Offline-Cache

## Starten
Dateien entpacken und **den gesamten Ordner** auf einen HTTPS-Webhost (z. B. GitHub Pages) hochladen. `index.html` ist der Einstieg. Nicht nur die HTML-Datei hochladen. HTTPS ist für Mikrofon und PWA nötig. Für lokale Entwicklung z. B. `python -m http.server 8000` im Ordner starten und `http://localhost:8000` öffnen. Auf iPhone Safari: Teilen → Zum Home-Bildschirm.

## Speicherung
Aufgaben und Notizen liegen im `localStorage`, Audio in `IndexedDB` des jeweiligen Browsers. Daten werden **nicht** automatisch zwischen Geräten synchronisiert. Private Browsermodi, Website-Daten löschen oder Speichermangel können Daten entfernen. Regelmäßig ZIP-Sicherungen exportieren und außerhalb des Browsers speichern. Der Import ersetzt vorhandene Daten. Der Audioexport kann bei großen Aufnahmen viel Speicher benötigen.

## KI-Backend (noch nicht implementiert)
Eine echte KI-Anbindung erfordert einen separaten Backend-Endpunkt wie `POST /api/assistant`, der Anfragen annimmt, serverseitig Authentifizierung und Ratenlimits prüft und die KI-API mit einem **nur serverseitig** hinterlegten API-Schlüssel aufruft. Die App darf den API-Schlüssel niemals enthalten. Notizen und Audiodaten nur nach ausdrücklicher Nutzeraktion an den Server senden, Datenschutz und Aufbewahrung beachten. Sprache-zu-Text kann später über einen serverseitigen Transkriptionsendpunkt ergänzt werden. Diese Version hat **keine** echte KI und **keine** Transkription.

## Hinweise
Erinnerungen/Push, Kalender-Synchronisierung und Cloud-Login sind noch nicht enthalten. Die App ist statisch hostbar, benötigt kein Work und keine laufenden Backendkosten für die Basisfunktionen.
