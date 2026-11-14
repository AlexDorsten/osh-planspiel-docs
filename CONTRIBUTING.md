# Dokumentation pflegen

Dieses Repository ist der gemeinsame Einstieg für die Dokumentation der OSH-Planspiel-App. Texte werden auf Deutsch gepflegt. Technische Bezeichner entsprechen dem Quellcode.

## Änderung durchführen

1. Den tatsächlichen App-Stand und die betroffene Funktion prüfen.
2. How-to, Bedienung oder Betriebsbeschreibung an der passenden Stelle ändern. Versionsnummer und Datum sichtbar halten.
3. Im [Changelog](CHANGELOG.md) eine nachvollziehbare Änderung ergänzen. Eine Idee bleibt als geplant gekennzeichnet, bis sie implementiert und ausgeliefert ist.
4. Relative Links, Codebeispiele und Abbildungen kontrollieren. Für ausführbare Beispiele ist zusätzlich die Anwendungsarbeitskopie erforderlich.
5. Änderungen als Commit oder Pull Request in dieses öffentliche Repository übernehmen.

## Welche Inhalte gehören hierher?

Anleitungen, Architektur- und Regelbeschreibungen, dokumentierte Codebeispiele, Änderungsblätter, zusammengefasste Prüfnachweise sowie erklärende Abbildungen und PDFs. App-Quellen und Installationsartefakte bleiben im Anwendungsprojekt. Konkrete Server-Zugangsdaten, private Schlüssel und rohe Konferenzprotokolle gehören nicht zur Dokumentation.

Die fünf Originaldateien aus [Zenodo 17811561](originalmaterial/zenodo-17811561/README.md) sind als Quellenarchiv enthalten. Diese Kopien unverändert lassen; Bearbeitungen separat ablegen und kennzeichnen. Herkunft, Namensnennung und [Lizenzzuordnung](LIZENZ.md) bei neuen Materialien mitführen. Bei einer weiteren Zenodo-Version einen eigenen Ordner mit Metadaten und geprüften Prüfsummen anlegen.

## Lizenzzuordnung mit REUSE prüfen

[`REUSE.toml`](REUSE.toml) ordnet Dateien den belegten Urhebern und Lizenzen zu. Bei neuen Dateien prüfen, ob die passende Regel greift; für Fremdmaterial einen eigenen, ausreichend konkreten Eintrag oder eine `.license`-Begleitdatei mit dessen tatsächlichen Angaben anlegen. Vorhandene Angaben haben Vorrang. Bestehende Drittmaterialien nicht pauschal unter die Projektlizenz stellen.

Die erforderlichen vollständigen Lizenztexte liegen unter [`LICENSES/`](LICENSES/). [REUSE-Spezifikation](https://reuse.software/spec-3.3/) und [offizielle Anleitung](https://reuse.software/tutorial/).

Im Repository-Stamm ausführen:

```sh
reuse lint
```

Ohne dauerhaft installiertes REUSE, mit vorhandenem `uv`:

```sh
uv tool run --from 'reuse[charset-normalizer]' reuse lint
```

Die zusätzliche Zeichensatzerkennung ermöglicht die Prüfung auch ohne systemweit installiertes `libmagic`. Der Lauf darf keine fehlenden Lizenztexte oder fehlenden Urheber-/Lizenzangaben melden. Prüfsummen von Originaldateien und archivierten Skills bleiben unverändert; Metadaten werden über `REUSE.toml` zugeordnet.

## Vertrauliche Betriebsdaten vermeiden

[Datenschutz und Betriebsbeispiele](docs/datenschutz-und-betriebsbeispiele.md) gelten auch für historische Dokumente, PDF-Metadaten, Screenshots und Issues. Reale Serverdaten gehören in die lokale Betriebsdokumentation außerhalb dieses Repos. Beispielnamen im SDK-Prüfstand sind synthetisch; Live-Aufnahmen vor der Übernahme prüfen. Für Git-Commits eine GitHub-noreply-Adresse verwenden. Nach der Historienbereinigung frisch klonen und alte Branch-Historien nicht zurückführen.

## Historie und aktuelle Aussagen

Historische Updateblätter werden nicht rückwirkend so umgeschrieben, als hätten spätere Funktionen bereits existiert. Einen sichtbaren Verweis auf den aktuellen Stand ergänzen und neue Erkenntnisse im How-to, in „Stand und Abnahme“ und im Changelog festhalten.

Bei einem App-Release Quellstand, SDK-Version, Schema-/Ereignisversion und tatsächlich ausgeführte Prüfungen aktualisieren. Einen erfolgreichen lokalen Prüfstand nicht als Live-Abnahme bezeichnen.

Die anfänglichen Texte stammen aus der Dokumentation der Anwendungsarbeitskopie. Nach der Übernahme Änderungen bevorzugt hier pflegen und erforderliche Hinweise in der Arbeitskopie mitführen; keine abweichenden zweiten Fassungen stillschweigend weiterführen.
