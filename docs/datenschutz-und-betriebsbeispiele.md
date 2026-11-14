# Datenschutz und neutrale Betriebsbeispiele

Stand: **14. November 2026**.

Dieses Dokumentationsrepo enthält neutrale Beispiele für die Einbindung des Planspiels. Reale Betriebsadressen, private Benutzerverzeichnisse, genaue Raumzuordnungen und vertrauliche Serverkonfigurationen werden außerhalb des Repositories verwaltet.

## Platzhalter in den Anleitungen

| Beispiel oder Platzhalter | Bedeutung |
| --- | --- |
| `bbb.example.org`, `ideas.example.org` | Reservierte Beispieldomains; durch die lokal konfigurierte Zieladresse ersetzen. |
| Beispielraum A / Beispielraum B, `example-room-a` | Anonymisierte Raumbezeichnungen und Beispiel-Slug; keine produktiven Raumkennungen. |
| `/srv/osh-planspiel-example/…` | Beispiel für den lokalen Ablageort eines freigegebenen Pakets. |
| `<GREENLIGHT_CONTAINER>` | Name des zur jeweiligen Installation gehörenden Containers. |
| `<IDEAS_PORT>` | Lokal konfigurierter Port des Ideen-Speicherdienstes. |
| `<IDEAS_CONFIG_FILE>` | Pfad zur lokalen Dienstkonfiguration. |
| `<IDEAS_DATA_DIR>` | Verzeichnis für die raumbezogenen Ideen. |
| `<UPDATE_JOURNAL_DIR>`, `<INSTALLATION_STATE_DIR>` | Lokale Verzeichnisse für Updatejournal und Installationsnachweise. |

Platzhalter sind vor der Ausführung auf der jeweiligen Instanz aufzulösen. Die Dokumentation macht die bislang an konkrete Räume gebundenen Installer nicht automatisch auf andere Installationen übertragbar. Die dortigen Identitäts-, Konfigurations- und Integritätsprüfungen bleiben erforderlich. Lokale Entwicklungsadressen auf `127.0.0.1` und die Testports des SDK-Prüfstands sind Entwicklungsbeispiele, keine veröffentlichten Produktionszugänge.

## Bereinigte Materialien

- Konkrete Infrastrukturadressen, persönliche Installationspfade, Raumbezeichnungen und Betriebsdetails sind durch die genannten Beispiele ersetzt.
- Der Live-Screenshot mit tatsächlichen Anzeigenamen wurde aus den Repository-Dateien und der erreichbaren Branch-Historie entfernt. Die verbleibenden Bilder aus dem lokalen Prüfstand verwenden synthetische Testnamen.
- In vier historischen Bedienungs-PDFs wurde die tatsächliche Raumbezeichnung aus dem PDF-Inhalt entfernt und durch „Beispielkonferenz“ ersetzt. Das ist eine Datenschutzkorrektur; die dokumentierten Funktionsstände bleiben gleich.
- Private Commit-E-Mail-Adressen sind durch GitHub-noreply-Adressen ersetzt. Urheber, Beitragszuordnung, Projektname und die ausdrücklich gewünschte Maintainer-Nennung bleiben erhalten.
- Die fünf veröffentlichten Zenodo-Originaldateien und die archivierten Original-Skills bleiben unverändert. Ihre öffentlichen Urheber- und Lizenzangaben gehören zur Quellenattribution.

## Nach dem öffentlichen Neuaufbau

Das Repository wurde am 14. November 2026 unter dem bisherigen Namen öffentlich neu angelegt. Es beginnt mit einem einzigen neuen Start-Commit auf `main`; frühere Commits und Branches sind nicht Teil des neuen Repositories. Beide früheren Branch-Dateistände bleiben ausschließlich lokal gesichert. Bestehende Klone nicht mit der alten Historie zurückpushen oder zusammenführen. Nach Sicherung noch nicht veröffentlichter eigener Änderungen das Repository frisch klonen; benötigte Änderungen anschließend einzeln auf den neuen Stand übertragen.

Die 17 Issues und 22 Kommentare wurden aus den aktuellen, geprüften Textfassungen neu angelegt. Ihre alten Bearbeitungsverläufe wurden nicht übernommen. Ursprüngliche Autoren, Zeitpunkte und Reaktionen sind als Textangaben erhalten; technische GitHub-Autoren, Zeitstempel und Kommentar-IDs stammen aus dem Neuaufbau. Im Titel von Issue #8 ist die konkrete Betriebsadresse durch eine Beispieldomain ersetzt.

GitHub kann nicht mehr referenzierte Objekte, frühere Issue-Versionen und hochgeladene Anhänge gesondert aufbewahren. Diese Bereiche sind zusätzlich zu prüfen und gegebenenfalls über GitHubs Löschfunktionen beziehungsweise den Support zu entfernen. Eine neue Branch-Historie ist allein kein Nachweis für die Löschung sämtlicher GitHub-internen Kopien. [GitHub-Anleitung zur vollständigen Entfernung](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository).

## Neue Änderungen prüfen

Vor einem Upload Texte, PDFs, Screenshots und Metadaten prüfen. Für Beispiele reservierte Domains und synthetische Teilnehmerdaten verwenden. Keine Zugangsdaten, produktiven Raum-IDs, privaten E-Mail-Adressen oder persönlichen Serverpfade aufnehmen. Urheber- und Maintainer-Nennungen von vertraulichen Betriebsdaten unterscheiden. Lizenzprüfung mit `reuse lint` und Datenschutzprüfung sind getrennte Prüfungen.
