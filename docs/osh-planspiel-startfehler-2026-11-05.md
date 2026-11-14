# OSH-Planspiel: fehlende Bestätigung nach dem Spielstart

> Betriebsangaben sind anonymisierte Beispiele. [Platzhalter und Übertragung auf eine eigene Instanz](datenschutz-und-betriebsbeispiele.md) vor der Ausführung beachten.

Stand: 5. November 2026 · Korrekturversion **0.1.0-pilot.5**

## Ursache und Nachweis

Nach „Planspiel beginnen“ blieb pilot.4 bei „Aktion wird mit BBB abgeglichen“ stehen. Nach zehn Sekunden erschien der Hinweis, dass BBB die Aktion noch nicht bestätigt habe. Die Spielvorbereitung war für andere Personen weiterhin sichtbar; der Start wurde nicht gespeichert.

Das Serverprotokoll `/var/log/bbb-apps-akka/bbb-apps-akka.log` enthält um **20:29:55 UTC (21:29:55 MEZ)** den Fehler `Unsupported type: java.lang.Long`, ausgelöst in `JsonUtils.AnyJsonWriter` (`PostgresProfile.scala:43`). Das vorherige Sichtbarkeitsereignis war erfolgreich gespeichert worden. Damit war der Transport grundsätzlich erreichbar; der Fehler trat beim Schreiben der Startdaten auf.

Der Mischwert wurde mit `crypto.getRandomValues(new Uint32Array(1))[0]` erzeugt. Das erlaubt Zahlen bis 4.294.967.295. Werte oberhalb 2.147.483.647 werden auf dieser BBB-Installation als Java Long behandelt, den ihr JSON-Schreiber nicht unterstützt. Das betrifft ungefähr die Hälfte der erzeugten Werte und erklärt, warum frühere Starts funktionieren konnten.

Die anderen Hypothesen waren ein nicht mehr passendes Präsentationsrecht oder eine fehlerhafte Zuordnung der Rückmeldung. Der konkrete Schreibfehler am Zeitpunkt des Spielstarts und der reproduzierbare Zahlengrenztest belegen den Fehler in den Startdaten.

## Korrektur

- Neue Mischwerte liegen zwischen 1 und 2.147.483.647. Null wird erneut gezogen, da der verwendete Mischalgorithmus einen von null verschiedenen Wert benötigt.
- Die Zufallsquelle bleibt `crypto.getRandomValues`. Nur der zulässige Wertebereich wird begrenzt.
- Die Sendeprüfung fängt zu große Mischwerte zusätzlich ab, bevor eine nicht bestätigbare Aktion an BBB gesendet wird.
- Das bestehende Ereignisprotokoll bleibt Version 2. Die Wiedergabe vorhandener Spielstände und die Spielregeln werden nicht verändert.

## Prüfung

Vor der Korrektur schlugen die neuen Grenztests fehl, darunter der Fall 2.147.483.649 mit genau dem Fehler `Unsupported type: java.lang.Long`. Nach der Korrektur bestehen 23 Modell-, Rechte- und Regressionstests, die Typprüfung, der Build, vier Installertests und die Ruby-Syntaxprüfung.

Der lokale SDK-Prüfstand bildet die Zahlengrenze jetzt ebenfalls nach. Beim Browserstart wurde der zuvor problematische Zufallswert 2.147.483.649 gezielt vorgegeben. Die App erzeugte daraus den gültigen Mischwert 1; der Start wurde bestätigt und „Würfeln“ erschien. Ein Kontrollbefehl mit dem alten zu großen Wert wurde vom Prüfstand abgewiesen. Der Prüfstand ist ausschließlich lokal und wird nicht auf BBB installiert.

Die ursprünglichen Tests nutzten kleine feste Mischwerte und ein simuliertes Backend ohne diese Zahlengrenze. Dadurch blieb die Unverträglichkeit unentdeckt. Die neuen Tests prüfen nun sowohl den von der Oberfläche verwendeten Generator als auch die tatsächliche Startdatenstruktur an der Transportgrenze. Ein größerer Architekturumbau ist für diese Korrektur nicht erforderlich.

## Aktivierung

**Installiert und live bestätigt am 5. November 2026:** Die Ausführung wurde bestätigt. Alle sechs öffentlich ausgelieferten Dateien von pilot.5 stimmen mit den Prüfsummen des lokalen Releases überein. Die zunächst noch laufende Konferenz lud weiterhin pilot.4. Nachdem Alex diese beendet hatte, wurde in der neuen Konferenz der Script-Verweis auf pilot.5 direkt geprüft.

Beim erneuten Beitritt von „Planspiel-Abnahme“ war bereits eine Partie mit Admin und Alex erfolgreich gestartet: Phase Entwicklung, Admin auf Feld 3/8, bestätigter Würfelwurf 3, Perspektive Emotional und Zustand „Zeit zum Austauschen“. Damit sind Start, Würfelereignis und Wiederherstellung des Spielstands beim späteren Beitritt auf dem echten BBB-Backend nachgewiesen. Die Aktionen wurden von den vorhandenen Teilnehmenden ausgeführt, nicht vom Abnahme-Client. Ein eigener Zug dieses Clients und Teamwechsel wurden bei dieser Abnahme nicht getestet. Der Abnahme-Client hat anschließend nur seine eigene Verbindung beendet.

*Der ursprüngliche Live-Screenshot wurde zum Schutz persönlicher Anzeigenamen entfernt. Der dokumentierte Prüfstand bleibt erhalten.*

Das Paket liegt unter `/srv/osh-planspiel-example/osh-planspiel-startfix-20261105/`. Installationsbefehl auf dem BBB-Server:

```sh
sudo python3 -I /srv/osh-planspiel-example/osh-planspiel-startfix-20261105/install-pilot.py install
```

Es ist ein neues unveränderliches Release. Deshalb gilt es für die **nächste neu begonnene Konferenz** in Beispielraum A. Vorhandene Ergebnisse bei Bedarf exportieren, die bisherige Konferenz regulär beenden und eine neue beginnen. Nur den Browser neu zu laden lädt innerhalb eines laufenden Meetings weiterhin dessen festgelegte Plugin-Version.

Die Aktivierung benötigt interaktives sudo. Der Installer verändert nur den Planspiel-Verweis dieses Raums; Notes bleibt erhalten. Es wird kein neuer Spielserver installiert und kein BBB-Dienst neu gestartet.

Die Bedienungsanleitung für pilot.4 gilt für pilot.5 weiterhin. Ein vollständiger Durchlauf mit mehreren Personen und beiden Teamaufteilungen bleibt als erweiterte Spielabnahme sinnvoll.

Rückweg zur vorherigen Version pilot.4 (einschließlich des dortigen Startfehlers):

```sh
sudo python3 -I /srv/osh-planspiel-example/osh-planspiel-startfix-20261105/install-pilot.py rollback
```
