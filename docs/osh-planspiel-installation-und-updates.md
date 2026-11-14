# OSH-Planspiel für BBB 4.0 – Installation und Updates

> Betriebsangaben sind anonymisierte Beispiele. [Platzhalter und Übertragung auf eine eigene Instanz](datenschutz-und-betriebsbeispiele.md) vor der Ausführung beachten.

**Aktueller Einstieg, 6. November 2026:** Das [Implementierungs-How-to](osh-planspiel-implementierung-howto.md) beschreibt den Stand pilot.5 einschließlich beider Datenkanäle, eigener Spielzüge und Release-Erstellung. Der [Startfehler ist mit pilot.5 behoben und live bestätigt](osh-planspiel-startfehler-2026-11-05.md). Der Haupttext dieser Anleitung bleibt als Dokumentation der Erstversion erhalten.

**Aktuelles Funktionsupdate:** Für pilot.4 gelten [eigene Spielzüge und getrennte Leitungsrechte](osh-planspiel-update-eigene-spielzuege-2026-11-05.md). Die [Bedienungsanleitung mit Online-Spielregeln](osh-planspiel-bedienungsanleitung-online.md) erklärt den aktuellen Ablauf. Die nachstehende v0.2 dokumentiert die Erstinstallation.


Version **0.2**, Stand **5. November 2026**, App **0.1.0-pilot.1**.

**Ergänzung:** Die Erstversion wurde inzwischen in Beispielraum A geöffnet und geprüft. Für das vorbereitete Update 0.1.0-pilot.2 mit automatischer BBB-Teilnehmerauswahl gilt das [Updateblatt vom 5. November 2026](osh-planspiel-update-teilnehmerauswahl-2026-11-05.md). Die folgende Anleitung und PDF v0.2 dokumentieren die Erstversion.


Diese Fassung ersetzt die Architektur der Anleitung v0.1. Deren bereits erzeugte PDF bleibt als historischer Entwurf erhalten; maßgeblich ist diese Anleitung. **Die App benötigt keinen eigenen Spielserver.** Sie besteht aus statischen Dateien und nutzt die bestehenden BBB-Datenkanäle innerhalb einer Konferenz. TypeScript/React laufen kompiliert im Browser; auf dem BBB-Server ist dafür kein zusätzlicher Node-Prozess erforderlich.

**Prüfstand:** Build, Typprüfung und Spiellogiktests bestanden; das echte BBB-Plugin-SDK wurde mit zwei Browserclients an einer lokalen, nachgebildeten BBB-Hostschnittstelle getestet. Die echte BBB-Konferenz, die Serverinstallation und der unten beschriebene Greenlight-Raumadapter sind noch nicht live abgenommen. Der Installer prüft die installierte Greenlight-Verarbeitung zur Laufzeit, bevor er Beispielraum A ergänzt.

## 1. Lieferumfang und Voraussetzungen

- BBB 4.0 mit passendem Plugin-SDK. Dieses Release verlangt exakt **1.0.0-beta.3**; die Versionsangabe allein garantiert keine Funktion.
- Öffentlich erreichbare HTTPS-Adressen für Manifest, JavaScript und drei SVG-Spielpläne. In Clustern müssen diese Adressen vom BBB-Backend und allen Browsern erreichbar sein.
- Aktivierung beim Erstellen einer Konferenz durch das Portal/LMS oder durch die BBB-Konfiguration. Eine Moderatorenrolle allein erteilt keine Installationsrechte. Auf fremden Instanzen muss der Betreiber die Einbindung ermöglichen.
- Keine zusätzlichen API-Schlüssel, Anmeldedienste, App-Datenbanken oder WebSocket-Dienste. Der Browser erhält keinen BBB-API-Schlüssel.

Das Archiv `apps/osh-planspiel/output/release/osh-planspiel-0.1.0-pilot.1.tar.gz` enthält ausschließlich `plugin/` mit `manifest.json`, `OshPlanspielPlugin.js`, `release.json` und `boards/spielplan-{klar,werkstatt,dialog}.svg`. `SHA256SUMS` enthält die Prüfsummen des Archivs und des gesonderten Installers für bbb.example.org.

Die verwendeten BBB-Funktionen sind Apps-Galerie, eigener Hauptbereich und ein Datenkanal `game-events`. Das Manifest erlaubt das Hinzufügen von Einträgen nur der Person mit Präsentationsrecht; Ersetzen/Löschen ist nicht freigegeben. [Offizielle Plugin-Dokumentation](https://docs.bigbluebutton.org/plugins/).

## 2. Spielbetrieb und Daten

Die Spielleitung öffnet **OSH-Planspiel** in der Apps-Galerie und trägt 1–6 Namen sowie die Spielidee ein. Individuelle Figuren sind immer möglich; Teams ab vier Personen: 2+2, 2+3 beziehungsweise bei sechs 2+2+2 oder 3+3. Die Namensreihenfolge legt die Mitglieder der angezeigten Gruppen fest. Die Startposition wird ausdrücklich gewählt, weil die Regel noch offen ist. Für den Test wird die Verwendung aller 87 extrahierten Kartenpositionen bestätigt.

Die Person mit Präsentationsrecht würfelt, schließt Besprechungen ab und speichert das gemeinsam formulierte Fazit. Alle anderen sehen denselben Spielstand und nutzen BBB-Audio/Video für den Austausch. Beim Wechsel des Präsentationsrechts wechselt auch die Bedienberechtigung. Am Phasenende warten alle Figuren; ohne gespeichertes Fazit wird die nächste Phase nicht freigegeben.

BBB verteilt die Spielereignisse innerhalb der laufenden Konferenz. Daraus rekonstruieren die Browser denselben Zustand, auch nach Neuladen oder späterem Beitritt, soweit BBB die Kanalhistorie bereitstellt. Es gibt keine unabhängige serverseitige Spielregelprüfung: Die Spielleitung ist eine vertrauenswürdige Rolle. Die Berechtigungen des Datenkanals sind in der echten BBB-Konferenz zusätzlich zu prüfen.

**Speicherung:** Namen, Idee, Würfe, Kartenziehungen und gespeicherte Fazits liegen in der Konferenzhistorie des BBB-Datenkanals. Der Pilot bietet keine dauerhafte Spielstanddatenbank und keine Fortsetzung nach Ende der Konferenz oder Serverausfall. Vor dem Beenden werden die Fazits als Markdown und optional der Spielstand als JSON heruntergeladen. Ein JSON-Import in eine neue Konferenz ist noch nicht implementiert. Ein ungespeicherter Fazit-Entwurf ist lokal und geht beim Neuladen verloren. Eine BBB-Aufzeichnung ist kein zugesicherter Ersatz für den Export.

Offen bleiben die endgültige Stapelauswahl, automatische Abschlussfragen, Münzwertung sowie ein erneutes Mischen bei leerem Stapel. Der Pilot zieht am Abschlussfeld keine automatische Zusatzkarte; manuelles Ziehen ist möglich. Er mischt einen leeren Stapel nicht automatisch neu. Pro Konferenz wird ein Spiel begonnen. Breakout-Räume sind für dieses Release deaktiviert.

## 3. Einbindung auf einer beliebigen BBB-Instanz

1. BBB- und tatsächlich verwendete SDK-Version feststellen, beispielsweise über `bbb-conf --version` und die Einstellung `html5PluginSdkVersion` in Paketdatei und lokalem Override. Keine ganze Konfigurationsdatei mit Zugangsdaten weitergeben. SDK-Anforderungen nicht zur Umgehung einer Fehlermeldung lockern.
2. Archiv prüfen und die Dateien unverändert in einen **versionierten HTTPS-Pfad** legen. Bei einer üblichen Paketinstallation ist `/var/www/bigbluebutton-default/assets/plugins/osh-planspiel/0.1.0-pilot.1/` ein möglicher Ablageort, sofern Nginx ihn unter `/plugins/osh-planspiel/0.1.0-pilot.1/` ausliefert. Anbieterinstallationen können andere Pfade verwenden.
3. Manifest, JavaScript und alle drei SVGs per HTTPS aufrufen und gegen die ausgelieferten Bytes prüfen. JavaScript-Einstieg und SVG-Pfade sind relativ zum Release. Bei abweichenden Browser-Ursprüngen müssen passende CORS-Header für die Plugin-Dateien und deren Integritätsprüfung erlaubt sein. HTML-Loginseiten oder Weiterleitungen sind keine gültigen Assets.
4. Beim BBB-API-Aufruf **create** `pluginManifests` als JSON-Liste ergänzen. Das folgende Beispiel ist der Parameterwert vor der üblichen URL-Kodierung und Signierung durch die bestehende Integration:

   ```json
   [{"url":"https://bbb.example.org/plugins/osh-planspiel/0.1.0-pilot.1/manifest.json"}]
   ```

   Vorhandene Plugin-Einträge bleiben erhalten. Das Beispiel bezeichnet keine bereitgestellte Downloadadresse. Wie das Portal den Parameter weitergibt, muss der Betreiber für sein System prüfen. Für andere Portale ist der unten beschriebene OSEG-Installer nicht geeignet.
5. Eine **neue Konferenz** starten. Das Manifest wird beim Anlegen eingelesen; ein bereits laufendes Meeting übernimmt einen geänderten Parameter nicht zuverlässig. Nur den vorgesehenen Testraum beenden, keine fremden Konferenzen.
6. App in der Apps-Galerie öffnen und die Abnahme aus Abschnitt 6 durchführen.

BBB dokumentiert auch globale Plugin-Konfiguration und `pluginManifestsFetchUrl`. Für den Pilot genügt eine gezielte Raumaktivierung; eine globale Freischaltung ist nicht erforderlich. [BBB-API: create und Plugin-Parameter](https://docs.bigbluebutton.org/development/api/#create), [Konfigurationsdateien](https://docs.bigbluebutton.org/administration/configuration-files/).

## 4. Einbindung in Beispielraum A auf bbb.example.org

Der selbstständige Installer `apps/osh-planspiel/output/release/install-pilot.py` enthält alle Assets und den Raumadapter. Er ist ausschließlich auf den vorhandenen Container `<GREENLIGHT_CONTAINER>`, den Portalhost bbb.example.org, den vorhandenen Raum **Beispielraum A** und das oben genannte Release begrenzt. Er läuft auf dem BBB-Server mit Python 3 und root-Rechten.

Er führt folgende Schritte aus:

1. SDK exakt prüfen; Dateien und JavaScript-Integrität prüfen.
2. Den bestehenden Raum Beispielraum A anhand seiner UUID, Friendly-ID, Meeting-ID und des Providers prüfen. Es wird kein neuer Raum angelegt. Bei abweichender Identität wird abgebrochen.
3. In einer zurückgerollten Datenbanktransaktion die Raumkonfiguration und die vollständige Greenlight-Weitergabe bis zum BBB-API-Client vor und nach Ergänzung des Plugins prüfen. Der API-Client wird nur innerhalb dieses Prüfprozesses durch einen Empfänger ersetzt. Vorhandene Plugins, insbesondere die Notizen-Erweiterung, und alle übrigen Meeting-Optionen müssen erhalten bleiben. Es wird dabei keine Konferenz angelegt und keine bestehende beendet.
4. Statische Dateien unter `/var/www/bigbluebutton-default/assets/plugins/osh-planspiel/0.1.0-pilot.1/` ablegen. Ein vorhandenes Release mit anderen Bytes wird nicht überschrieben. Alle Dateien über das Portal per HTTPS vergleichen.
5. Ausschließlich den `pluginManifests`-Wert von Beispielraum A in einer Transaktion ergänzen. Falls die globale Optionsdefinition noch fehlt, wird sie mit leerem Standardwert `[]` ergänzt. Andere bereits bestehende Räume erhalten dadurch keine zusätzlichen Optionswerte; künftig neu angelegte Räume können den leeren Standard erben. Bestehende Definitionen und fremde Plugin-Einträge bleiben erhalten.
6. Raumadresse und Ergebnis in `<INSTALLATION_STATE_DIR>/installation.json` speichern und ausgeben. Es werden weder BBB noch Greenlight neugestartet; ein zusätzlicher Dienst wird nicht eingerichtet.

Die konkrete Greenlight-Verarbeitung basiert auf [RoomSettingsGetter](https://github.com/bigbluebutton/greenlight/blob/master/app/services/room_settings_getter.rb), [MeetingStarter](https://github.com/bigbluebutton/greenlight/blob/master/app/services/meeting_starter.rb) und [BigBlueButtonApi](https://github.com/bigbluebutton/greenlight/blob/master/app/services/big_blue_button_api.rb), jeweils am 5. November 2026 gelesen. Der Laufzeitcheck ist erforderlich, weil die installierte Instanz davon abweichen kann.

Vorbereiteter Ablageort auf dem Server:

```sh
cd /srv/osh-planspiel-example/osh-planspiel-pilot-20261105
sha256sum -c SHA256SUMS
sudo python3 -I install-pilot.py check
sudo python3 -I install-pilot.py install
```

Das sudo-Passwort wird ausschließlich im eigenen Terminal eingegeben. Der Installer besitzt weder ein Passwort noch eine automatische sudo-Freigabe. Bei abweichendem SDK, unbekanntem Raum, fehlendem Greenlight-Vertrag oder nicht erreichbaren HTTPS-Dateien hält er an. Falls die statischen Dateien bereits kopiert wurden, aber die Raumaktivierung scheitert, bleiben sie ungenutzt liegen. Ein erneuter Lauf ist bei identischem Release möglich. Zielraum: [Beispielraum A](https://bbb.example.org/rooms/example-room-a/join). Die Aktivierung gilt beim nächsten Anlegen der Konferenz. Ein laufendes Meeting wird nicht verändert oder beendet.

## 5. Updates, Rückweg und Backups

Ein Update erhält eine **neue Versionsnummer und einen neuen Verzeichnispfad**. Das bestehende Manifest oder JavaScript wird nicht unter derselben Versionsadresse ersetzt. Die Build-Pipeline erzeugt das neue Manifest mit passendem SHA-384-Integritätswert. Änderungen an Karten, Regeln und Ereignisschema werden in den Release-Hinweisen dokumentiert.

Ablauf: Typprüfung/Tests/Build → neue statische Dateien bereitstellen → HTTPS und Integrität prüfen → in einer separaten Testkonferenz abnehmen → gespeicherte Raum-Manifestadresse auf die neue Version umstellen → neue Konferenz beginnen. Laufende Spiele werden vorher exportiert und mit ihrer begonnenen Version beendet. Ein Zustandsumzug zwischen Versionen ist für den Pilot nicht zugesichert.

Für einen Rückweg wird bei künftigen Updates die vorige Manifestadresse wieder in der Raumkonfiguration eingesetzt und eine neue Konferenz begonnen. Beide Release-Verzeichnisse bleiben während der Abnahme erhalten. Der aktuelle OSEG-Installer ist auf die Erstversion und Beispielraum A festgelegt; er ist kein universeller Updater und muss mit jedem freigegebenen Release neu erstellt und geprüft werden.

Den vorbereiteten Erstpilot für **zukünftige** Konferenzen deaktivieren:

```sh
sudo python3 -I /srv/osh-planspiel-example/osh-planspiel-pilot-20261105/install-pilot.py disable
```

Dies entfernt nur die genaue OSH-Manifestadresse aus Beispielraum A. Der Raum, fremde Plugins, die allgemeine Optionsdefinition und die statischen Dateien bleiben erhalten. Eine laufende Konferenz bleibt unverändert; sie muss regulär beendet werden, bevor die Deaktivierung beim nächsten Start greift.

Für den Betrieb sichern: freigegebene Release-Dateien/Prüfsummen, Portal-/Raumkonfiguration, Installerbericht und exportierte Fazits. Eine bestehende Greenlight-Datenbanksicherung erfasst die Raumoption; sie ist **keine** Sicherung des aktuellen Spiels. Ob statische Plugin-Dateien im vorhandenen Serverbackup enthalten sind, muss der Betreiber ausdrücklich prüfen.

## 6. Abnahme in der echten Konferenz

- App lädt in Beispielraum A; andere Räume und das zweite Portal bleiben ohne zusätzliche OSH-Aktivierung.
- Mindestens zwei Browser sehen Positionen, Karten und gespeicherte Fazits identisch. Später Beitritt und Neuladen rekonstruieren den Zustand.
- Präsentierende können bedienen; Zuschauende können keine Ereignisse schreiben. Übergabe des Präsentationsrechts funktioniert.
- Solo, Einzelmodus sowie 2+2, 2+3, 2+2+2 und 3+3 sind auswählbar. Jede Person gehört genau einer Figur an.
- Ein hoher Wurf stoppt am Phasenende. Wartende Figuren werden übersprungen. Der Wechsel ist erst nach Ankunft aller und gespeichertem Fazit möglich.
- Audio/Video, Bildschirmfreigabe und Rückkehr zur Präsentation funktionieren während des Spiels. Darstellung mit geöffnetem Chat und auf kleinen Fenstern prüfen.
- Alle sechs Fazits lassen sich herunterladen. Nach Konferenzende wird kein dauerhafter Spielstand versprochen.
- Neue Konferenz mit deaktiviertem Manifest lädt die App nicht mehr.

Abnahmeprotokoll: BBB-/SDK-/App-Version, Portal, Datum, Browser, getestete Modi, Befunde und verantwortliche Person festhalten. Bis diese Abnahme vorliegt, bleibt das Release ein Pilot.
