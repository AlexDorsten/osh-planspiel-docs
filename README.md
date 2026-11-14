# OSH-Planspiel – Dokumentation

Das OSH-Planspiel basiert auf **„How To: Open Source Hardware“ Board Game** von **Dorothea Schneider, Natalie Früholz, Florian Rabis und Katarzyna Wiesenhütter** (2025), veröffentlicht auf [Zenodo, DOI: 10.5281/zenodo.17811561](https://doi.org/10.5281/zenodo.17811561). Das Spiel entstand im Rahmen von **OSHOP – Open Source Hardware Innovation Plattform**; die [HTW Dresden beschreibt die Entwicklung und den Einsatz des Planspiels](https://www.htw-dresden.de/news/spielerisch-open-source-hardware-entdecken-oshop-planspiel-bringt-komplexe-themen-in-die-anwendung).

**Lizenz: [Creative Commons Namensnennung 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.de)**, wie im Zenodo-Eintrag ausgewiesen. Die [fünf Originaldateien](originalmaterial/zenodo-17811561/README.md) sind unverändert enthalten. Für unsere eigenen Dokumentations- und Spielmaterial-Bearbeitungen übernehmen wir ebenfalls CC BY 4.0. Die BBB-Fassung ergänzt unter anderem Online-Spielabläufe, Spielansichten und individuelle Fragen. [Lizenztext](LICENSE) · [Namensnennung, Änderungen und Geltungsbereich](LIZENZ.md). Eigenständige Drittmaterialien behalten ihre jeweiligen Lizenzen; die Softwarelizenz des separat verwalteten App-Codes wird damit nicht festgelegt.

Das Repository wird unter **AlexDorsten/osh-planspiel-docs** geführt. **Florian Rabis ist ebenfalls Maintainer des Projekts.**

**Betriebsbeispiele:** Adressen, Serverpfade und Raumbezeichnungen sind anonymisierte Beispiele. Das öffentliche Repository wurde am 14. November 2026 unter demselben Namen mit einem einzigen neuen Start-Commit neu angelegt. Die bisherige Git-Historie wurde nicht übernommen; bestehende Klone bitte frisch klonen. [Platzhalter, Datenschutz und Umgang mit alten Klonen](docs/datenschutz-und-betriebsbeispiele.md).

Die maschinenlesbare Zuordnung von Dateien, Urhebern und Lizenzen steht in [`REUSE.toml`](REUSE.toml); die zugehörigen Lizenztexte liegen unter [`LICENSES/`](LICENSES/). [Prüfung und Pflege](CONTRIBUTING.md#lizenzzuordnung-mit-reuse-prüfen).

Öffentliches Dokumentationsrepository für die Planspiel-App in BigBlueButton 4.0. Stand: **10. November 2026**, dokumentierter Quellstand: **0.1.0-pilot.13**. Vier neue Ideen erhalten je 87 Fragen; OpenShelf und UniProKit Maxi bleiben unverändert bei je 47. Lokal geprüft, Serveraktivierung und native Abnahme dieser Fassung noch offen. pilot.12 ist inzwischen für beide Räume eingerichtet.

## Einstieg

| Ziel | Dokument |
| --- | --- |
| Originalmaterialien, Herkunft und Lizenz nachlesen | [Zenodo-Dateien](originalmaterial/zenodo-17811561/README.md) · [Lizenzzuordnung](LIZENZ.md) |
| App verstehen und weiterentwickeln | [Implementierungs-How-to](docs/osh-planspiel-implementierung-howto.md) |
| Aktuellen Funktions- und Prüfstand kennen | [Stand und Abnahme](docs/stand-und-abnahme.md) |
| Online-Spiel vorbereiten und spielen | [Bedienung und Spielregeln](docs/osh-planspiel-bedienungsanleitung-online.md) · [PDF, Stand pilot.12](pdf/OSH-Planspiel_Bedienungsanleitung_Online_v0.1.0-pilot.12.pdf) |
| Installation und Updates durchführen | [Aktueller Ablauf im How-to](docs/osh-planspiel-implementierung-howto.md#11-in-bbb-einbinden-und-aktualisieren) |
| Individuelle Kartensets nutzen und aktivieren | [Vier neue 87er-Sets und gemeinsames Raumupdate](docs/osh-planspiel-update-vier-ideen-2026-11-10.md) |
| Ideen anlegen, dauerhaft speichern und aktualisieren | [Update pilot.11](docs/osh-planspiel-update-ideen-2026-11-07.md) |
| Aktualisierte Spielpläne drucken | [Drei Spielpläne als A3-PDF v0.2](pdf/OSH-Planspiel_Spielplaene_v0.2.pdf) |
| Änderungen nachverfolgen | [Changelog](CHANGELOG.md) |
| Mögliche KI-Unterstützung auswählen | [KI-Funktionen: Nutzen, Beispiele und Betriebswege](docs/ki-funktionen-konzept.md) |
| Bisher verwendete Agents und Skills nachvollziehen | [Rollenprofile und Skill-Archiv](agents-und-skills/README.md) |
| Würfelentwurf beurteilen | [Animation: Stand und geplante Anbindung](docs/wuerfelanimation.md) |
| Dokumentation pflegen | [Pflegehinweise](CONTRIBUTING.md) |

## Technischer Überblick

Die App verwendet TypeScript, React und das BBB-Plugin-SDK 1.0.0-beta.3. Statische Dateien werden auf dem vorhandenen BBB-Server ausgeliefert; native BBB-Datenkanäle synchronisieren die Spielereignisse. Für die Ideenverwaltung läuft ein kleiner lokaler Speicherdienst auf demselben BBB-Server; die Ideen werden je Raum in einer portierbaren JSON-Datei aufbewahrt. Ein zusätzlicher Rechner wird nicht benötigt.

Es spielen 1–6 Personen. Ab vier Personen sind die vereinbarten Teamaufteilungen möglich. Die aktive Person bedient ihren Zug; die BBB-Präsentatorrolle bleibt bei der Spielleitung. Alle Figuren warten am Phasenende aufeinander, bevor das gemeinsame Fazit und der Phasenwechsel erfolgen.

Der Betrieb von pilot.5 ist in Beispielraum A auf bbb.example.org nachgewiesen. Spielstart und ein Würfelwurf wurden direkt in BBB beobachtet. Eine vollständige Live-Abnahme aller Teamaufteilungen und Phasen steht noch aus.

## Umfang und Quellstand

Dieses Repository enthält Anleitungen, Versionsnotizen, eine Bedienungs-PDF, Abbildungen, die fünf unveränderten Zenodo-Originaldateien sowie ein Archiv der Agent-Rollen und konsultierten Skill-Anleitungen. Die App-Quellen, SDK-Abhängigkeiten, Installationspakete, weitere Arbeitsmaterialien und Serverkonfigurationen werden separat verwaltet. Codeblöcke im How-to dienen als dokumentierte Beispiele.

Für ausführbare Entwicklungsbefehle wird die Anwendungsarbeitskopie mit `apps/osh-planspiel/` benötigt. Pfade dieses Namens in den Dokumenten beziehen sich auf jene Arbeitskopie. [Quellstand und Prüfungen](docs/quellstand-und-pruefungen.md) halten die zugehörigen Dateiprüfsummen fest.

Die Markdown-Anleitungen beschreiben pilot.13; die bisherige Bedienungs-PDF bleibt ausdrücklich der ältere Stand pilot.12. Beide Fassungen arbeiten mit sechs persönlichen Ansichten (1–3 und 7–9). Die dritte Phase heißt „Verteilung“. Die drei Bitmap-Spielpläne zeigen dort acht getrennte Felder; die sechs gleich großen Sektoren orientieren sich an der freigegebenen Referenz. Frühere PDFs und Abbildungen bleiben als historische Stände erhalten. Die Würfelanimation ist ein Entwurf und noch kein Bestandteil dieser App-Version.

Das [KI-Konzept](docs/ki-funktionen-konzept.md) beschreibt unter anderem Fazit-Assistent, Perspektiven-Coach, Solospiel-Begleitung und mögliche Transkriptunterstützung. Es enthält Vorschläge für spätere Erweiterungen; auch pilot.13 besitzt diese Funktionen noch nicht.

## Historische Änderungsblätter

- [Erstinstallation und Updates, Betreiberanleitung v0.2](docs/osh-planspiel-installation-und-updates.md)
- [pilot.2: Teilnehmerauswahl](docs/osh-planspiel-update-teilnehmerauswahl-2026-11-05.md)
- [pilot.3: Warteansicht, als eigenständige Version nicht aktiviert](docs/osh-planspiel-update-warteansicht-2026-11-05.md)
- [pilot.4: Eigene Spielzüge, Teamwechsel und Rechte](docs/osh-planspiel-update-eigene-spielzuege-2026-11-05.md)
- [pilot.5: Startkorrektur und Live-Nachweis](docs/osh-planspiel-startfehler-2026-11-05.md)
- [pilot.6: Erste sechs persönliche 2D-/3D-Ansichten](docs/osh-planspiel-update-ansichten-2026-11-06.md)
- [pilot.7: Erste Bitmap-Ansichten 7–9](docs/osh-planspiel-update-bitmap-2026-11-06.md)

- [pilot.8: Erste zusammenhängende Tischszenen](docs/osh-planspiel-update-tischszenen-2026-11-06.md)

- [pilot.9: Glatte Brettkonturen, räumlicher Würfel und entfernte Ansichten 4–6](docs/osh-planspiel-update-grafik-2026-11-06.md)

Diese Blätter bewahren den jeweiligen damaligen Stand. Für aktuelle Implementierungs- und Betriebsfragen mit dem How-to und „Stand und Abnahme“ beginnen.
