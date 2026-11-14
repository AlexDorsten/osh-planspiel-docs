# OSH-Planspiel: Ansicht für Mitspielende

> Betriebsangaben sind anonymisierte Beispiele. [Platzhalter und Übertragung auf eine eigene Instanz](datenschutz-und-betriebsbeispiele.md) vor der Ausführung beachten.

**Nachfolger:** Diese noch nicht aktivierte Version wird durch [pilot.4 mit eigenen Spielzügen](osh-planspiel-update-eigene-spielzuege-2026-11-05.md) ersetzt. Die nachfolgende Beschreibung dokumentiert den vorherigen Stand.

Stand 5. November 2026, Update **0.1.0-pilot.3** für Beispielraum A auf bbb.example.org. Lokal gebaut und geprüft, zur Aktivierung auf dem Server bereitgestellt. Noch nicht live aktiviert.

Ohne BBB-Präsentationsrecht erscheint vor Spielbeginn ausschließlich die Warteansicht: „Der Präsentator startet das Spiel. Bitte gedulde dich einen Moment. Der Präsentator bereitet das Spiel vor.“ Die Vorbereitung mit Personen, Teamaufteilung, Spielidee, Startposition, Materialbestätigung und Startbutton wird nicht angezeigt.

Auch während des Spiels sind ausschließlich für Präsentierende bestimmte Bedienelemente ausgeblendet: Würfeln, Zusatzfrage, Zugabschluss, Fazitbearbeitung, Speichern und Phasenwechsel. Mitspielende sehen weiterhin Spielplan, Fragen und gespeicherte Fazits. Lokale Anzeigeoptionen, Leseansichten und Exporte stehen weiterhin zur Verfügung.

Die App wechselt nach dem gemeinsamen Start automatisch von der Warteansicht zum Spielplan. Eine manuelle Übergabe des BBB-Präsentationsrechts aktualisiert die sichtbaren Bedienelemente automatisch. **Der Spielerwechsel überträgt keine BBB-Rechte:** Wie bisher bedient die Spielleitung alle Figuren. Eine automatische Übergabe oder individuelle Spielberechtigungen wurden nicht ergänzt.

## Aktivierung

Auf dem BBB-Server:

```sh
cd /srv/osh-planspiel-example/osh-planspiel-warteansicht-20261105 &&
sha256sum -c SHA256SUMS &&
sudo python3 -I install-pilot.py install
```

Der Installer verwendet einen neuen Versionspfad, ersetzt nur die bekannten OSH-Manifestverweise im bestehenden Raum und prüft den Erhalt anderer Plugins und Meeting-Optionen. Änderungen gelten beim nächsten Konferenzstart. Eine laufende Konferenz bleibt unverändert; vor deren regulärem Ende gegebenenfalls Fazits exportieren. Ein Neuladen des Browsers allein wechselt nicht die Manifestversion einer laufenden Konferenz.

Rückweg auf Version 0.1.0-pilot.2, sofern deren unveränderte Dateien vorhanden sind:

```sh
sudo python3 -I /srv/osh-planspiel-example/osh-planspiel-warteansicht-20261105/install-pilot.py rollback
```

## Prüfung

Typprüfung, Build, Ruby-Syntax und vier Paket-/Installationsschutztests bestanden. Im lokalen Prüfstand mit echtem BBB-SDK und zwei Browserclients wurden geprüft: keine Vorbereitungselemente bei Mitspielenden, Anzeigewechsel bei Übergabe/Entzug des Präsentationsrechts, Spielstart durch Präsentierende, automatischer Wechsel zum Spielplan im zweiten Client, ausgeblendeter Würfelbutton und reine Leseansicht des gemeinsamen Fazits ohne Bearbeitungs-/Fortsetzen-Buttons. Die Warteansicht wurde visuell geprüft. Der Live-Test dieser neuen Version steht nach Aktivierung noch aus.
