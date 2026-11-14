# OSH-Planspiel: eigene Spielzüge und offene Vorbereitung

> Betriebsangaben sind anonymisierte Beispiele. [Platzhalter und Übertragung auf eine eigene Instanz](datenschutz-und-betriebsbeispiele.md) vor der Ausführung beachten.

> Historisches Änderungsblatt. Aktueller Stand: [pilot.5 und Abnahme](stand-und-abnahme.md). Die nachfolgenden Statusangaben beziehen sich auf die damalige Prüfung.

Stand: 5. November 2026 · Version **0.1.0-pilot.4** · Ziel: bestehender Raum **Beispielraum A** auf **bbb.example.org**.

Dieses Update ersetzt die nicht aktivierte Warteansicht-Version 0.1.0-pilot.3. Der Nutzer hat den Installer ausgeführt. Alle sechs öffentlichen Release-Dateien stimmen mit dem geprüften Build überein. In Beispielraum A wurde die tatsächliche Einbindung von pilot.4 anhand der geladenen Plugin-Adresse bestätigt. Direkt in BBB geprüft: Bestätigung des Leitungs-Datenkanals, später Beitritt (Auswahl wächst von 1 auf 2), Warteansicht ohne Präsentationsrecht, Startfreigabe nach Kartenbestätigung und Aktualisierung beim Verlassen. Beide eigenen Testsitzungen wurden ohne Audio/Kamera wieder abgemeldet. Es wurde keine Partie begonnen; der vollständige Würfel- und Teamtest in BBB steht noch aus.

Prüfnachweise: `output/player-turns-verification.json` und `output/player-turns-live-assets-verification.json`.

## Verhalten

- Vor dem Spielstart aktualisiert BBB die Teilnehmerauswahl laufend. Später Beigetretene erscheinen zur Auswahl. Ohne manuelle Auswahl werden bis zu sechs aktuelle Personen vorausgewählt; eine bereits bewusst getroffene Auswahl bleibt erhalten und lässt sich ergänzen. Mehr als sechs oder mehr als aktuell anwesende Personen können nicht starten.
- Mit „Planspiel beginnen“ wird die Besetzung festgelegt. Ein späterer Beitritt erweitert ein laufendes Spiel nicht.
- Die aktive Person würfelt selbst, zieht gegebenenfalls eine zusätzliche Frage und bestätigt „Besprochen – weiter“. Die übrigen Personen lesen und diskutieren mit; fremde Zugknöpfe werden ausgeblendet.
- In Teams wechseln sich die Mitglieder nach jedem abgeschlossenen Figurenzug ab. Dieselbe Person bedient Würfeln und Besprechung innerhalb ihres Zugs. Die Reihenfolge setzt sich über Phasengrenzen fort. Teams, die schon am Phasenende warten, werden übersprungen.
- Die Person mit BBB-Präsentationsrecht ist Spielleitung. Sie bereitet das Spiel vor, schreibt das gemeinsame Fazit, bedient gegebenenfalls Zusatzfragen im Phasenabschluss und eröffnet die nächste Phase. Als Mitspieler darf sie nur im eigenen Zug würfeln.
- Die BBB-Präsentatorrolle wird durch einen Spielerwechsel nicht geändert. Ein manueller BBB-Präsentatorwechsel überträgt lediglich die Spielleitung.
- Nach einem Wiedereintritt mit neuer BBB-Kennung kann die Spielleitung unter „Abwesende Mitspielende neu zuordnen“ einen bestehenden Spielplatz einer anwesenden, noch nicht zugeordneten Person zuweisen. Die Besetzung wird dadurch nicht vergrößert; Figur, Reihenfolge, Spielname und Fazits bleiben erhalten. Es gibt keine automatische Zuordnung anhand möglicherweise gleicher Namen.

Die bisherigen Regeln bleiben bestehen: 1–6 Personen; Einzelmodus bei jeder Anzahl; Teams bei 4 als 2+2, bei 5 als 2+3 und bei 6 als 2+2+2 oder 3+3; Halt auf Feld 8; gemeinsames schriftliches Fazit vor dem Phasenwechsel.

## Installation auf bbb.example.org

Das installierte Paket liegt unter `/srv/osh-planspiel-example/osh-planspiel-eigene-zuege-20261105/`. In einer SSH-Sitzung auf dem Server ausführen:

```sh
cd /srv/osh-planspiel-example/osh-planspiel-eigene-zuege-20261105
sha256sum -c SHA256SUMS
sudo python3 -I install-pilot.py check
sudo python3 -I install-pilot.py install
```

Das Passwort wird ausschließlich lokal am sudo-Prompt eingegeben. Der Installer prüft die exakte Raumidentität, das SDK 1.0.0-beta.3, Paketprüfsummen und die öffentliche HTTPS-Auslieferung. Erst danach setzt er den Plugin-Verweis für Beispielraum A. Das Notes-Plugin und übrige Raumoptionen bleiben erhalten. Es wird kein zusätzlicher Dienst installiert und kein Server neu gestartet.

Die Konfiguration gilt für die **nächste neu begonnene Konferenz** dieses Raums. Eine laufende Konferenz wird nicht beendet. Zuvor Fazits exportieren, die bisherige Konferenz regulär beenden und anschließend neu beginnen; bloßes Neuladen eines Browsers erzeugt keine neue Konferenz. Das Ereignisprotokoll dieser Version ist Version 2. Ein Spiel aus einem älteren Plugin wird nicht in diese Version importiert.

Öffentliches Manifest:
`https://bbb.example.org/plugins/osh-planspiel/0.1.0-pilot.4/manifest.json`

## Rückweg

Rückkehr zu pilot.2, der zuletzt auf dem Server nachgewiesenen Vorgängerversion:

```sh
sudo python3 -I install-pilot.py rollback
```

Der Installer prüft vor dem Wechsel alle pilot.2-Dateien gegen die bekannten Prüfsummen und ihre HTTPS-Auslieferung. Auch dieser Wechsel gilt für die nächste Konferenz. `sudo python3 -I install-pilot.py disable` entfernt nur den verwalteten Planspiel-Verweis für künftige Konferenzen.

## Technische Grundlage

Die App bleibt statisch auf dem BBB-Server. Zwei native BBB-Datenkanäle tragen das gemeinsame Ereignisprotokoll:

| Kanal | BBB-Schreibrecht | Verwendung |
| --- | --- | --- |
| `game-events` | `presenter` | Start, Fazits, Phasenwechsel, Ansicht, Neuzuordnung |
| `game-turns` | `all` | Würfeln und Besprechung der aktiven Person |

Beide Kanäle verbieten Ersetzen und Löschen. Das Spiel prüft bei der Wiedergabe den Kanal sowie `createdBy` aus den BBB-Metadaten gegen die gespeicherte Teilnehmerzuordnung. Eine im Nutzdatenobjekt behauptete Identität wird ignoriert. Zusätzliche Fragen und deren Bestätigung im Phasenabschluss laufen über den Leitungskanal. Die offizielle [BBB-Plugin-Dokumentation](https://docs.bigbluebutton.org/plugins/) beschreibt die Kanalberechtigungen; die Struktur der Metadaten ist zusätzlich am fest eingebundenen SDK geprüft.

Revisionen ordnen Ereignisse beider Abonnements. Bei einer noch fehlenden Vorgängerrevision wartet die Wiedergabe auf weitere Daten. Zeitgleiche Befehle auf derselben Revision werden deterministisch entschieden; der unterlegene Befehl muss bewusst wiederholt werden. Bestätigungen berücksichtigen Kanal und BBB-Absender, damit ein fremdes Ereignis mit gleicher Nutzdaten-ID keine eigene Aktion bestätigen kann.

## Abnahme in BBB nach Aktivierung

1. Zwei Browser mit unterschiedlichen BBB-Personen beitreten lassen. Nur eine Person hat Präsentationsrecht. Die andere sieht vor dem Start die Warteansicht.
2. Weitere Personen vor dem Start beitreten lassen. Ihre Namen müssen in der laufenden Auswahl erscheinen; maximal sechs auswählen.
3. Einzelmodus starten: Nur die aktive Person sieht „Würfeln“ und anschließend „Besprochen – weiter“. Der Zug wechselt nach Bestätigung, die BBB-Präsentatorrolle bleibt erhalten.
4. In einer weiteren Testkonferenz Teams wählen. Nach dem nächsten Zug derselben Figur bedient das nächste Teammitglied; bei 3er-Teams alle drei Personen prüfen.
5. Alle Figuren auf Feld 8 bringen. Nur die Spielleitung bearbeitet das Fazit. Erst nach dem Speichern ist der Phasenwechsel möglich; alle sehen denselben Stand.
6. Eine Person neu verbinden. Bei gleicher Kennung bleibt die Zuordnung bestehen; bei neuer Kennung ordnet die Spielleitung den bisherigen Platz neu zu. Ein anderer, weiterhin besetzter Spielplatz darf nicht übernommen werden.
7. Spielstand und Fazits exportieren, bevor die Konferenz endet.

Die automatischen Modelltests und der lokale Browserprüfstand decken Rechte, Teamrotation, Phasenwechsel und späte Beitritte ab. Der Prüfstand simuliert den BBB-Transport und wird nicht ausgeliefert. Die Vorbereitung ist inzwischen auf der aktualisierten BBB-Instanz geprüft. Spielzüge, Teamrotation und Phasenwechsel bleiben für die gemeinsame Live-Abnahme offen.
