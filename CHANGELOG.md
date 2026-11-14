# Changelog

Dieses Changelog unterscheidet Änderungen der Dokumentation von App-Releases. Der Eintrag einer geplanten Funktion bedeutet keine Auslieferung. Historische Einträge wurden am 6. November 2026 aus den vorhandenen Änderungs- und Prüfunterlagen zusammengestellt.

## Dokumentation – 2026-11-14

- Öffentliches Repository unter unverändertem Namen neu angelegt: ein neuer Start-Commit auf `main`, keine Übernahme der bisherigen Commit-Historie oder des alten Maintainer-Branches. Aktuelle Dokumentation, Originalmaterialien, Lizenzzuordnung und Quellenangaben bleiben erhalten. 17 Issues und 22 Kommentare aus geprüfter lokaler Sicherung wieder angelegt; ursprüngliche Autoren, Zeitpunkte und sieben Reaktionen als Text erhalten.

- Datenschutzbereinigung: konkrete Infrastrukturangaben und persönliche Pfade durch dokumentierte Beispiele ersetzt, Live-Screenshot mit echten Anzeigenamen aus allen erreichbaren Commits entfernt, vier Bedienungs-PDFs inhaltlich bereinigt und die private Commit-E-Mail auf GitHub-noreply umgestellt. Beide Branch-Historien neu geschrieben; ursprüngliche Urheber und Maintainer bleiben genannt.
- Betriebsbeispiele und Hinweise zum frischen Klonen ergänzt. Die veröffentlichten Zenodo-Originale und archivierten Skills bleiben bytegleich. PDF-Korrekturen mit dem lokalen PDF-Skill gerendert und geprüft; Quellenprüfung und REUSE-Prüfung erneut durchgeführt.

- `REUSE.toml` mit getrennten Zuordnungen für eigene Dokumentation, Spielbearbeitungen, die fünf Zenodo-Originaldateien und archivierte Apache-2.0-Skills ergänzt. Original-Urheber und Projektbeiträge getrennt; Maintainer-Rolle bleibt eine eigene Angabe.
- Den unveränderten Zenodo-Metadaten-Snapshot gemäß Zenodo-Richtlinie separat unter CC0 1.0 eingeordnet. Die fünf Spieldateien bleiben unter CC BY 4.0.
- Vollständige Lizenztexte unter `LICENSES/` ergänzt; bisherige Lizenzdateien, NOTICE und Originaldateien bleiben unverändert. README, Lizenzzuordnung und Pflegeanleitung um REUSE-Verweise und Prüfbefehl erweitert.
- Geprüft mit REUSE 6.3.0: `reuse lint` erfolgreich nach Spezifikation 3.3; 89 von 89 relevanten Dateien mit Urheber- und Lizenzangaben, keine fehlenden oder ungenutzten Lizenzen. Alle acht Prüfsummen des Zenodo-Archivs und sieben Skill-Archivdateien weiterhin unverändert.

## Dokumentation – 2026-11-13

- Florian Rabis bei der Nennung des Repositories in der README zusätzlich als Maintainer des Projekts ausgewiesen.
- Herkunft des Spiels direkt am Anfang der README ergänzt: OSHOP, „How To: Open Source Hardware“ Board Game, alle vier Urheber und DOI [10.5281/zenodo.17811561](https://doi.org/10.5281/zenodo.17811561).
- Alle fünf auf Zenodo veröffentlichten Dateien unverändert unter [`originalmaterial/zenodo-17811561/`](originalmaterial/zenodo-17811561/README.md) übernommen: Spielplan als PDF/PPTX, Anleitung als PDF/DOCX und Fragekarten als XLSX. Originalnamen und Dateiinhalte erhalten; Dateigrößen und sämtliche Zenodo-MD5-Prüfsummen geprüft, SHA-256-Manifest und Metadaten-Snapshot ergänzt.
- Offiziellen Lizenztext **CC BY 4.0** übernommen; diese Lizenz ist im genannten Zenodo-Eintrag ausgewiesen. Die frühere CC-BY-SA-Angabe wird für diesen Eintrag durch den belegten Lizenznachweis ersetzt. [Geltungsbereich](LIZENZ.md), Namensnennung und Änderungen der digitalen Bearbeitung dokumentiert; eigene Dokumentations- und Spielmaterial-Bearbeitungen ebenfalls unter CC BY 4.0. Drittmaterialien und separat verwalteter App-Code gesondert abgegrenzt.
- Erneuten Einsatz des lokalen PDF-Skills für Text- und Sichtprüfung der Original-PDFs im Skill-Archiv dokumentiert. Keine Änderung des App-Verhaltens oder Serverinstallation.

## App 0.1.0-pilot.13 – vorbereitet am 2026-11-10

- Vier neue individuelle Kartensets mit jeweils 87 Fragen: USB-C-Werkzeug-Akkusystem, Kindergarten-Laubkompost, verteilte OSEG-Ideenplattform und UniDocKit. Grundlage sind die gespeicherten Beschreibungen, einschließlich der ausführlicheren Fassungen in OSH-Planspiel.
- Je Set 15/15/14/15/14/14 Fragen in Entwicklung, Produktion, Verteilung, Nutzung, Lebensende und Grundlagen. Insgesamt 348 unterschiedliche neue Fragen.
- OpenShelf und UniProKit Maxi bleiben einschließlich ihrer 47 Fragen und Kennungen unverändert; der Originalstapel ebenfalls.
- Sechs Sets in der Auswahl, automatische Zuordnung der vier neuen Ideen anhand ihrer vorhandenen Kennung oder ihres Titels, tatsächliche Anzahlen und Phasenverteilung sichtbar.
- Gemeinsamer Updateaufruf für Beispielraum A und Beispielraum B; beide Plugin-Verweise in einer Datenbanktransaktion, andere Apps und Ideenbestände bleiben erhalten. Rückweg zur installierten pilot.12.
- 44 TypeScript-Tests, Typprüfung, Build/Paket, zwölf Python-Installations-/Updateprüfungen und vier Ruby-Tests bestanden. Browserprüfung inklusive späterem Beitritt, Wiederladen und schmaler Ansicht erfolgreich. Aktivierung und native BBB-Abnahme offen.
- [Alle vier Fragenlisten, Prüfung und Aktivierungsbefehl](docs/osh-planspiel-update-vier-ideen-2026-11-10.md). Bedienung, How-to und Quellstand aktualisiert; die bisherige PDF bleibt als gekennzeichneter Stand pilot.12 erhalten.

## App 0.1.0-pilot.12 – vorbereitet am 2026-11-07

- Je 47 individualisierte Fragen für UniProKit Maxi (Maßstab 2:1) und Modular OpenShelf; die zwölf angenommenen Entwürfe je Idee bleiben erhalten und werden um jeweils 35 ergänzt.
- Direkt unter der Originalauswahl eine alternative Auswahl für individuelle Karten samt Set-Vorauswahl und manueller Zuordnung. Beide Modi schließen sich gegenseitig aus; nur die Spielleitung bereitet sie vor.
- Auf Nutzerwunsch phasenweises Ziehen: 8/8/8/8/8/7 Karten, ohne Wiederholung, Vermischung oder automatisches Neumischen. Leere Phasen blockieren den Spielablauf nicht.
- Gemeinsame Set-Kennung, nummerierte Karten mit Phase, Phasenvorrat und Set im Ergebnisexport. Ereignisprotokoll 3; Originalhistorien mit Protokoll 2 bleiben lesbar.
- 42 TypeScript-Tests, Typprüfung, Build/Paket, sechs Installertests und Browserprüfung erfolgreich. Paket auf dem BBB-Server geprüft; sudo-Aktivierung und native Abnahme offen.
- [Vollständige Fragenlisten, Bedienung und Installation](docs/osh-planspiel-update-kartensets-2026-11-07.md); Anleitung und PDF aktualisiert.

## App 0.1.0-pilot.11 – vorbereitet am 2026-11-07

- Einstieg mit „Idee anlegen“, „Idee speichern“ und „Idee löschen“, Auswahl gespeicherter Titel sowie getrennten Titel-/Beschreibungsfeldern.
- Modular OpenShelf als einmalige Startvorlage mit vier kurzen Beschreibungszeilen aus der Präsentation. Community-Satz auf Nutzerwunsch entfernt, um diesen Spielaspekt offen zu halten.
- Dauerhafte Ideen je Konferenzraum in einer portierbaren JSON-Datei auf dem BBB-Server; keine Ideen-Import-/Exportfunktion. Kleiner lokaler Python-Speicherdienst mit BBB-Präsentatorprüfung, Dateisperre, atomaren Schreibvorgängen und Konflikterkennung.
- Titel und Beschreibung als unabhängige Kopie im Spielstand; Beschreibung für alle Teilnehmenden aufklappbar und im Ergebnisexport enthalten. Alte Spielstände ohne Beschreibung bleiben lesbar.
- 36 TypeScript-Tests, Typprüfung, Build/Paket und gezielte Speicher-/Authentifizierungsprüfungen erfolgreich; Browserprüfung mit zwei Personen und getrennten Räumen. Native Installation/Live-Abnahme noch offen.
- Sichtbare Überschrift „Meine Ansicht“ über der Auswahl entfernt; zugängliche Beschriftung für Screenreader bleibt erhalten.
- Bedienung, PDF, How-to, Quellstand und Screenshots aktualisiert. [Änderungen und Aktivierung](docs/osh-planspiel-update-ideen-2026-11-07.md).

## App 0.1.0-pilot.10 – vorbereitet am 2026-11-06

- Dritte Phase heißt durchgängig **Verteilung**: Spieldaten, Oberfläche, Fazitexport, drei 2D-SVGs und drei Bitmap-Spielpläne. Technische ID `distribution` bleibt erhalten.
- In Bitmap-Ansichten 7–9 die fehlerhafte Feldaufteilung korrigiert: acht einzelne Felder, Fragezeichen und weißer Kreis jeweils auf eigener Kachel. Alle sechs Sektoren an der freigegebenen Sechstel-Aufteilung geprüft.
- 24 Marker der betroffenen Phase neu vermessen; ein benachbarter Werkstattmarker um wenige Pixel nachgeführt. Konturmasken und Ansichten 1–3/7–9 bleiben erhalten.
- 33 Anwendungstests, Typprüfung, Build/Paket, vier Installertests und Ruby-Syntax bestanden. Bildkorrekturen und Figuren auf Feldern 1/5/6 unabhängig im Browser geprüft. Bitmap-Geometrie ist eine Illustration; die Sektorprüfung berücksichtigt perspektivische Ableseunsicherheit.
- Bedienungs-PDF pilot.10 inklusive aktuellem Screenshot und Spielplan-PDF v0.2 neu erstellt, gerendert und visuell geprüft; How-to, KI-Konzept und Changelog aktualisiert. Historische Dateien bleiben erhalten.
- Paket auf dem Server bereitgestellt und Prüfsummen bestätigt; Aktivierung benötigt sudo. Rückweg: installierte und anhand aller zwölf Dateien verifizierte pilot.9. [Änderungen und Aktivierung](docs/osh-planspiel-update-verteilung-2026-11-06.md).

## App 0.1.0-pilot.9 – vorbereitet am 2026-11-06

- Ansichten **4–6 entfernt**. Sechs Optionen mit stabilen Nummern **1–3 und 7–9**; gespeicherte Auswahl der entfernten Varianten wird auf die entsprechende Bitmap-Ansicht umgestellt.
- Neu vermessene, tangentenstetige Konturmasken erhalten den ganzen Brettkörper; feine Alpha-Kante und anliegender Schatten beseitigen den groben Polygonzuschnitt. Original-PNGs und alle 48 Markerpositionen unverändert.
- Perspektivischer, gerundeter Würfel mit kubischen Proportionen, Bodenkontakt und Augen auf allen drei sichtbaren Flächen. Oben steht der bestätigte Wurf; Gegenflächen ergeben sieben. Neutralzustand mit korrekt orientiertem Fragezeichen. Keine Wurfanimation.
- 31 Anwendungstests, Typprüfung, Build/Paket, vier Installertests und Ruby-Syntax bestanden. Unabhängige Grafikprüfung aller drei Bretter und aller sechs Würfelergebnisse bestanden; Zweipersonentest und 620-Pixel-Inhaltsbereich geprüft.
- Paket übertragen, Prüfsummen bestätigt. Aktivierung benötigt sudo; native Live-Abnahme offen. Rückweg ist die nachgewiesene pilot.7, da pilot.8 nur bereitgestellt wurde.
- Bedienung, How-to, Quellstand und neue Screenshots aktualisiert. [Grafikupdate und Installationsbefehl](docs/osh-planspiel-update-grafik-2026-11-06.md).

## App 0.1.0-pilot.8 – vorbereitet am 2026-11-06

- **Ersetzt die Ansichten 7–9**, ohne neue Optionen anzulegen. Ansichten 1–6, Brettgrafiken und alle 48 Markerkoordinaten bleiben unverändert.
- Zusammenhängende Tischszene mit drei passenden Bitmap-Oberflächen, Papierkante, pinkem Kartenrahmen, Bodenschatten und integrierter Kopf- und Figurenleiste.
- Sichtbarer Kartenstapel zeigt die verbleibenden Karten; ruhender Würfel zeigt ausschließlich den bestätigten Wurf, davor ein Fragezeichen. Keine Wurfanimation und keine zusätzlichen Spielaktionen.
- Fazitverweis im scrollenden Karteninhalt; Container-Regeln für kleinere BBB-App-Bereiche. Bestehende Zugrechte und Bedienaktionen erhalten.
- 28 Anwendungstests, Typprüfung, Build/Paket, vier Installertests und Ruby-Syntax erfolgreich. Drei Tischszenen und längere Frage visuell geprüft; zwei Teilnehmer mit Ansichten 7/8, eigenen Würfen und identischen Anzeigen getestet.
- Zwölf statische Dateien; drei neue Hintergrund-PNGs. Paket zur Aktivierung mit interaktivem sudo bereitgestellt; native Live-Abnahme offen. Rückweg auf die auf dem Server geprüfte Version pilot.7.
- Dokumentation und Screenshots aktualisiert. [Ansichten und Installationsbefehl](docs/osh-planspiel-update-tischszenen-2026-11-06.md).

## App 0.1.0-pilot.7 – vorbereitet am 2026-11-06

- Neue Ansichten **7–9**: Bitmap-Tischmodell, Bitmap-Werkstatt und Bitmap-Spiellandschaft. Der ganze illustrierte Rundkurs stammt aus den vorhandenen PNG-Entwürfen. 48 gemessene Markerpositionen pro Bild führen die beweglichen Hütchen; keine Feldnummern.
- Alle neun Optionen nummeriert. Persönliche Auswahl bleibt lokal je BBB-Kennung; bestehende IDs und gemeinsame Spielregeln bleiben erhalten. Legende bei den Bitmap-Ansichten zuschaltbar; Ersatzdarstellung bei Bildladefehler.
- Schwebende rechte Seitenleiste mit dezentem Schatten in allen 3D-Ansichten 4–9; flache Seitenleiste und Kreise in 2D erhalten.
- 28 Anwendungstests, Typprüfung, Build/Paket, vier Installertests und Ruby-Syntax erfolgreich. Alle neun Ansichten im Browser geprüft; zwei Teilnehmer mit unterschiedlichen Bitmap-Ansichten, eigenen Würfen, identischem Spielstand und wiederhergestellter Auswahl getestet.
- Neun statische Release-Dateien, keine zusätzlichen Bilddateien oder Dienste. Paket übertragen und Prüfsummen bestätigt; Aktivierung von pilot.7 verlangt weiterhin interaktives sudo. Die vorhandenen pilot.6-Dateien wurden für den Rückweg nachgewiesen; eine native Spielabnahme der neuen Ansichten steht aus.
- How-to, Bedienung, Quellstand, Abnahme und README aktualisiert. [Ansichten, Screenshots und Aktivierungsbefehl](docs/osh-planspiel-update-bitmap-2026-11-06.md).

## App 0.1.0-pilot.6 – vorbereitet am 2026-11-06

- Sechs persönliche Ansichten: 2D Klar/Werkstatt/Dialog und 3D Tischmodell/Werkstattmodell/Spiellandschaft. Auswahl lokal je BBB-Kennung; keine Synchronisierung der Ansicht über die Spielkanäle.
- Hütchen nur in 3D; runde Figuren in 2D erhalten. Der räumliche Ring wird mit 48 gleichwinkligen Feldern aus den bestehenden Daten erzeugt; keine Feldnummern. Gemeinsame Regeln und Positionen bleiben unverändert.
- Drei PNG-Illustrationen ergänzen die statischen Dateien. Keine neue Bibliothek, kein WebGL und kein zusätzlicher Dienst. Neun Dateien im Release.
- 27 Anwendungstests, Typprüfung, Build, vier Installertests und Ruby-Syntax erfolgreich. Lokaler Zweipersonentest mit unterschiedlichen Ansichten, beiden eigenen Würfen und wiederhergestellter Auswahl bestanden.
- Paket auf dem bestehenden BBB-Server bereitgestellt. Aktivierung benötigt interaktives sudo; pilot.6 ist noch nicht als installiert oder live abgenommen bestätigt. Rückweg führt zu pilot.5.
- Bedienungsanleitung, How-to, Quellstand und Abnahme aktualisiert. [Details und Aktivierung](docs/osh-planspiel-update-ansichten-2026-11-06.md).

## App: noch nicht veröffentlicht

- Würfelanimation als Gestaltungsentwurf: Flugbewegung, Aufprallen, Hüpfen und Ausrollen; korrigierte Endperspektive und Bodenschatten mit der 5 auf der Oberseite.
- Die Animation ist noch nicht in BBB eingebaut. Echte Würfe benötigen sechs mögliche Endergebnisse oder eine parametrisierte Darstellung und eine Anbindung an bestätigte Ereignisse.
- Vollständige Live-Abnahme von Teamrotation, allen Phasen und Wiederbeitritt ist noch ausstehend.

## Dokumentation – 2026-11-06

### Hinzugefügt

- Ordner `agents-und-skills/` mit Hauptagent und drei Fachagent-Profilen, neun dokumentierten Skill-Fassungen, davon drei Originalanleitungen mit Apache-Lizenz und sechs Nutzungsprofile mit Herkunft, sowie SHA-256-Manifest. Nachgewiesener Einsatz und bloße Lektüre getrennt; Herkunft und Nachweisgrenzen dokumentiert und in der README verlinkt. Reine Dokumentationsergänzung ohne App-Release.
- Konzept zu denkbaren KI-Funktionen: Fazit-Assistent, Perspektiven-Coach, Solospiel-Begleitung, Ergebnisberichte, Sprach- und Wissenshilfe sowie spätere Transkriptanbindung. Nutzen, Beispiele, Betriebswege, Integrationspunkte und Pilotprüfungen beschrieben; in der README verlinkt. Es wurden keine KI-Funktionen in der App aktiviert.
- Eigenständiges privates Dokumentationsrepository unter `AlexDorsten/osh-planspiel-docs`.
- Entwickler-How-to für pilot.5: lokaler Aufbau, Quellcodeübersicht, BBB-Adapter, Datenmodell, Kanäle und Rechte, ausführbares Replay-Beispiel, lokaler Zweipersonentest, Release-Erstellung und Einbindung.
- Anleitung für die geplante Würfelanimation mit Trennung von bestätigtem Spielergebnis und lokaler Darstellung.
- Übersicht über Funktionsstand, offene Abnahmen und bekannte Grenzen.
- Changelog, Pflegehinweise und Prüfsummen des dokumentierten Quellstands.
- Bestehende Bedienungsanleitung einschließlich PDF sowie historische Installations- und Updateblätter zusammengeführt.

### Geprüft

- 23 TypeScript-Tests, Typprüfung und Build erfolgreich.
- Vier Installertests und Ruby-Syntaxprüfung erfolgreich.
- Ausführbares Beispiel aus dem How-to gegen die aktuelle Modellimplementierung geprüft.

## App 0.1.0-pilot.5 – 2026-11-05

### Behoben

- Gelegentlich unbestätigter Spielstart: Der Mischwert für den Kartenstapel wird auf positive signed-32-Bit-Werte begrenzt. Dadurch wird der auf dieser BBB-Installation beobachtete Fehler `Unsupported type: java.lang.Long` vermieden.
- Zusätzliche Prüfung zu großer Mischwerte vor dem Absenden der Startaktion.

### Geprüft und installiert

- Grenzwerttests und lokaler Prüfstand bilden die BBB-Zahlenbeschränkung nach.
- Release-Dateien installiert und über HTTPS mit den erwarteten Prüfsummen verglichen.
- Nach Neubeginn von Beispielraum A wurde pilot.5 geladen; gestartete Partie, bestätigter Würfelwurf und Wiederherstellung beim späteren Beitritt wurden beobachtet.
- Der Nutzer bestätigte anschließend, dass der Startfehler nicht mehr auftritt.
- Ereignisprotokoll bleibt Version 2; Spielregeln und Bedienung bleiben gegenüber pilot.4 unverändert.

## App 0.1.0-pilot.4 – 2026-11-05

### Hinzugefügt und geändert

- Aktive Mitspielende würfeln und bestätigen den eigenen Zug selbst.
- Teammitglieder wechseln nach jedem abgeschlossenen Figurenzug; die Reihenfolge setzt sich über Phasengrenzen fort.
- Getrennte native Kanäle: `game-events` für die Spielleitung und `game-turns` für zugeordnete Spieleraktionen.
- Ereignisprotokoll 2 mit Absenderprüfung aus BBB-Metadaten, Revisionen und Bestätigungsschlüsseln aus Kanal, Absender und Ereignis-ID.
- Teilnehmerliste bleibt bis zum Spielstart offen für später Beigetretene.
- Spielleitung kann einen abwesenden Spielplatz nach Wiedereintritt einer neuen BBB-Kennung zuordnen.
- Die BBB-Präsentatorrolle wird beim Zugwechsel nicht übertragen.

### Installation und Prüfung

- In Beispielraum A installiert; native Teilnehmeraufnahme, Leitungsansicht und Warteansicht geprüft.
- Übernimmt die vorbereitete Warteansicht aus pilot.3.
- Zu diesem Zeitpunkt noch kein vollständiger nativer Würfel-/Teamtest; die anschließende Startkorrektur ist unter pilot.5 dokumentiert.

## App 0.1.0-pilot.3 – 2026-11-05

### Vorbereitet, nicht separat aktiviert

- Warteansicht ohne Vorbereitungsformular für Teilnehmende ohne Präsentationsrecht.
- Ausschließlich für die Spielleitung bestimmte Bedienelemente wurden ausgeblendet.
- Lokal gebaut und geprüft; vor Live-Aktivierung durch pilot.4 ersetzt. Die damalige vollständige Steuerung durch die Spielleitung ist kein aktueller Bedienstand.

## App 0.1.0-pilot.2 – 2026-11-05

### Hinzugefügt

- Vorauswahl aus der vollständigen BBB-Teilnehmerliste statt Platzhalternamen.
- Höchstens sechs anwesende Personen; Bots ausgeschlossen, gleiche Anzeigenamen unterscheidbar.
- Auswahl und Reihenfolge vor Spielbeginn ändern; Anzahl, Namen und IDs unmittelbar vor Start prüfen.
- Teilnehmerzuordnung nach Spielstart bewahren.

### Historischer Status

- Das ursprüngliche Updateblatt beschrieb zunächst die Bereitstellung. Die spätere pilot.4-Dokumentation benennt pilot.2 als zuvor auf dem Server nachgewiesene Version.

## App 0.1.0-pilot.1 – 2026-11-05

### Erstpilot

- Statisches TypeScript-/React-Plugin mit BBB-Galerieeintrag und gemeinsamem Hauptbereich.
- Native BBB-Synchronisierung ohne zusätzlichen Spielserver; zunächst Bedienung durch die präsentierende Person.
- Sechs Phasen, 48 Felder, 87 extrahierte Kartenpositionen und drei Spielplangestaltungen.
- Einzel- und vereinbarte Teammodi, Halt am Phasenende, gemeinsames Fazit sowie Markdown-/JSON-Export.
- Versionsgebundener Installer für Beispielraum A mit Integritäts- und Raumprüfung.
- In Beispielraum A geöffnet und gemeinsame App-Ansicht geprüft.

## Dokumentationspflege

Bei jeder fachlichen, technischen oder betrieblichen Änderung diesen Verlauf ergänzen. Geplante, lokal geprüfte und tatsächlich installierte Änderungen ausdrücklich unterscheiden. Für neue App-Versionen auch die zugehörige Dokumentation und den Abnahmestand aktualisieren; Dokumentationsänderungen allein erhöhen nicht die App-Version.
