# OSH-Planspiel: Teilnehmerauswahl aus BBB

> Betriebsangaben sind anonymisierte Beispiele. [Platzhalter und Übertragung auf eine eigene Instanz](datenschutz-und-betriebsbeispiele.md) vor der Ausführung beachten.

> Historisches Änderungsblatt. Aktueller Stand: [pilot.5 und Abnahme](stand-und-abnahme.md). Die nachfolgenden Statusangaben beziehen sich auf die damalige Prüfung.

Stand 5. November 2026. **Update von 0.1.0-pilot.1 auf 0.1.0-pilot.2**, ausschließlich Beispielraum A auf bbb.example.org.

## Ergebnis und Stand

Version 0.1.0-pilot.1 wurde nach der Installation direkt in Beispielraum A geöffnet. Die gemeinsame App-Ansicht und die gesperrte Bedienung ohne Präsentationsrecht waren sichtbar; auch die Notizen-Erweiterung blieb in BBB verfügbar. Die sechs öffentlichen Release-Dateien wurden per HTTPS mit den lokalen Dateien verglichen: alle identisch. Die private root-Installationsdatei konnte über den SSH-Benutzer ohne sudo-Passwort nicht gelesen werden.

Die neue Version 0.1.0-pilot.2 ersetzt die vier Platzhalternamen durch die aktuelle BBB-Teilnehmerliste. Sie ist lokal geprüft und unter `/srv/osh-planspiel-example/osh-planspiel-update-20261105/` auf dem Server zur Aktivierung bereitgestellt; sie ist noch nicht aktiviert.

## Verhalten der neuen Auswahl

- Alle verfügbaren menschlichen BBB-Teilnehmenden sind anfangs ausgewählt, höchstens sechs. Bots werden nicht als Mitspielende behandelt.
- Personen können vor dem Spiel abgewählt werden. Bei mehr als sechs Anwesenden kann die Spielleitung die Auswahl ändern; eine siebte Auswahl ist gesperrt.
- Die Reihenfolge lässt sich per Pfeiltasten ändern und bestimmt im Teammodus die Zusammensetzung. Die bekannten Teamgrößen bleiben unverändert.
- Neue Teilnehmende erscheinen automatisch in der Liste. Nach einer ausdrücklich geänderten Auswahl werden sie nicht ungefragt ins Spiel aufgenommen. Abwesende Personen können vor Spielbeginn nicht ausgewählt bleiben.
- Gleiche Anzeigenamen bleiben anhand ihrer BBB-Benutzer-IDs unterscheidbar; für die Anzeige werden nötigenfalls Nummern ergänzt.
- Unmittelbar vor dem Absenden des Spielstarts werden Auswahl, Anzahl, Namen und IDs gegen die aktuelle Liste geprüft. Ein Teilnehmender kann nur einmal gewählt werden.
- Nach Spielstart wird die Besetzung festgehalten. Verlassen oder Neuladen verändert ein laufendes Spiel nicht und entfernt keine Figuren. Die Zuordnung ist in Spielstand und Export enthalten.

Die App verwendet `useUsersBasicInfo` aus dem festgelegten SDK 1.0.0-beta.3, nicht die nur teilweise sichtbare Teilnehmerliste. Ein neuer Backenddienst ist nicht erforderlich. Die Regelkontrolle bleibt wie bisher im vertrauenswürdigen Präsentierenden-Client; eine unabhängige serverseitige Spiellogik wird nicht behauptet.

## Update installieren

Auf dem BBB-Server:

```sh
cd /srv/osh-planspiel-example/osh-planspiel-update-20261105 &&
sha256sum -c SHA256SUMS &&
sudo python3 -I install-pilot.py install
```

Der Installer legt die neue Version in einem separaten statischen Verzeichnis ab. Er ersetzt nur den bisherigen OSH-Manifestverweis im bestehenden Raum. Die Verarbeitung von Greenlight wird vor und nach dem Wechsel geprüft: andere Plugins und Meeting-Optionen müssen identisch bleiben. Die vorige Version und deren Installationsbericht werden aufbewahrt. Bei unbekannten OSH-Versionen oder abweichenden Raumkennungen bricht er ab.

Das Update gilt für die **nächste neu angelegte Konferenz**. Eine laufende Konferenz wird weder beendet noch umgestellt; auch ein bloßes Neuladen des Browsers lädt deren bereits festgelegtes Manifest erneut. Zuerst gegebenenfalls Fazits exportieren und die Konferenz regulär beenden, dann Beispielraum A neu starten. Für BBB, Greenlight und andere Räume ist kein Dienstneustart vorgesehen.

Danach prüfen: Die Namen entsprechen den Anwesenden, die Zahl der auswählbaren Spieler überschreitet weder die Anwesenheit noch sechs, die Teamzuordnung ist korrekt, und der gemeinsame Spielstart funktioniert mit einem zweiten Browser. Dieser Live-Test der neuen Version steht noch aus.

## Rückweg

Falls der neue Pilot einen Fehler zeigt:

```sh
sudo python3 -I /srv/osh-planspiel-example/osh-planspiel-update-20261105/install-pilot.py rollback
```

Der Rückweg prüft die Originalprüfsummen der unverändert vorhandenen Version 0.1.0-pilot.1 und deren HTTPS-Auslieferung. Danach wird nur der OSH-Manifestverweis wieder auf die vorige Version gesetzt. Er greift ebenfalls beim nächsten Konferenzstart. `disable` entfernt die bekannten OSH-Pilotverweise aus dem verwalteten Raum für künftige Konferenzen; fremde Plugins und Dateien bleiben bestehen.

## Prüfung

Typprüfung und Build bestanden. Zwölf TypeScript-Tests einschließlich Anwesenheitsprüfung unmittelbar vor Spielstart und vier Paket-/Installationsschutztests bestanden; Ruby-Syntax geprüft. Im lokalen Browserprüfstand mit echtem SDK wurden Vorauswahl, sechs von acht Anwesenden, Abwahl/Neuauswahl, Abgänge vor dem Start, Übernahme der Namen ins Spiel und Erhalt der Figuren nach einem Abgang geprüft. Der Prüfstand ersetzt nicht den noch ausstehenden Test der neuen Version in BBB.

Die [allgemeine Betreiberanleitung](osh-planspiel-installation-und-updates.md) und deren PDF v0.2 beschreiben die Erstinstallation. Für diesen konkreten Versionswechsel gilt dieses Ergänzungsblatt.
