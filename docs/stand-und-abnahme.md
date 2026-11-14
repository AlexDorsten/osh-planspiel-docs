# Aktueller Stand und Abnahme

Stand: **10. November 2026** · Quellstand **0.1.0-pilot.13** (lokal geprüft; Aktivierung und native Live-Abnahme offen). Zuletzt live bestätigt: **pilot.5** · SDK **1.0.0-beta.3** · Ereignisprotokoll **3**, Originalhistorien mit Protokoll 2 lesbar.

## Implementiert

- Alternative Original-/Individualauswahl; sechs Sets: zwei unveränderte mit je 47 und vier neue mit je 87 phasenbezogenen Fragen, gemeinsamer Set-Kennung und Wiederherstellung beim späteren Beitritt.

- Ideenverwaltung mit Titel, Beschreibung, Auswahl und drei Aktionsbuttons; raumweise gegliederte, dauerhafte JSON-Datei auf demselben BBB-Server. Server prüft Präsentatorrecht für jeden Zugriff.
- TypeScript-/React-Plugin im BBB-Hauptbereich mit sechs persönlichen Ansichten: drei in 2D (1–3) und drei vollständige Bitmap-Spielpläne (7–9) mit fester Perspektive.
- Lokale Auswahl je BBB-Kennung, Hütchen ausschließlich in 3D, runde Figuren weiterhin in 2D. 48 Felder ohne Feldnummern in allen 3D-Ansichten; Bitmap-Figuren folgen den gemessenen Markermittelpunkten. Schwebende Seitenleiste in allen 3D-Ansichten.
- Überarbeitete Tischszenen ausschließlich in den bestehenden Ansichten 7–9: passende Bitmap-Oberflächen, Papierkarte, bestätigter Würfelwert und reale Kartenanzahl. Glatte Körperkonturen und räumlicher Würfel mit Augen auf allen sichtbaren Flächen; Ansichten 4–6 entfernt, gespeicherte Auswahl wird migriert. Ansichten 1–3 bleiben erhalten.
- Synchronisierung über zwei native BBB-Datenkanäle; kein zusätzlicher Spielserver.
- 1–6 Personen; eigene Figuren oder Teams ab vier Personen: 2+2, 2+3, 2+2+2 oder 3+3.
- Vorauswahl aktueller Konferenzteilnehmer, laufende Aktualisierung vor Spielbeginn und feste Besetzung nach Start.
- Eigene Zugbedienung durch die aktive Person; Teammitglieder wechseln sich ab.
- Spielleitung mit BBB-Präsentationsrecht für Vorbereitung, Fazits und Phasenwechsel. Kein automatischer Präsentatorwechsel.
- Sechs gleich große Sektoren mit acht Feldern; dritte Phase „Verteilung“, getrennte Frage-/Weißfelder in allen Bitmap-Ansichten. Halt auf Feld 8, gemeinsames gespeichertes Fazit vor dem Phasenwechsel.
- Markdown-Fazitexport und JSON-Spielstandexport.
- Explizite Neuzuordnung eines abwesenden Spielplatzes nach Wiedereintritt mit neuer BBB-ID.
- Begrenzter Mischwert zur Vermeidung des beobachteten BBB-Startfehlers.

## Geprüft

| Ebene | Nachweis |
| --- | --- |
| Lokal, am 10. November | Typprüfung, 44 TypeScript-Tests, Build/Paket, zwölf Python-Installations-/Updateprüfungen, vier Ruby-Tests erfolgreich |
| Kartensets pilot.13 | Sechs Vorauswahlen, 87er-Spielstart, passende Frage, später Beitritt, Neuladen und schmale Ansicht im Browser; vollständiger Verbrauch aller sechs Sets im Modelltest |
| Ideenverwaltung pilot.11 | Anlegen, Bearbeiten, Löschdialog, Wiederladen, getrennte Räume, Warteansicht und gemeinsame Beschreibung im Browser geprüft; Dateikopie und Neustart im Speichertest |
| Grafik-/Bezeichnungstest pilot.10 | Drei korrigierte Bitmap-Spielpläne, Figuren auf Frage- und Weißfeld, Beschriftung in 2D/3D/Export sowie neue PDFs geprüft |
| Lokaler Zweipersonentest pilot.9 | Konturen 7–9 und alle Würfelwerte unabhängig visuell geprüft; 620-Pixel-Inhaltsbereich geprüft; zwei Teilnehmer mit unterschiedlicher Auswahl, identischen Positionen, Würfelwerten und Kartenanzahlen; keine Ereignisse durch Ansichtswechsel |
| How-to | Ausführbares Ereignisbeispiel: Anna würfelt eine 3, schließt ihren Zug ab, Ben ist aktiv |
| Installation | Sechs öffentlich ausgelieferte pilot.5-Dateien stimmen mit dem freigegebenen Release überein |
| Native BBB-Vorbereitung | Aktuelle Namen, später Beitritt, Leitungsansicht, Startfreigabe und Warteansicht geprüft |
| Native BBB-Partie | pilot.5 geladen; gestartete Partie und bestätigter Wurf 3 beim späteren Beitritt sichtbar |
| Nutzerrückmeldung | Startfehler tritt nicht mehr auf |

Die beobachtete Live-Partie wurde von den vorhandenen Teilnehmenden bedient. Der Prüfclient hat sie lesend nachvollzogen und anschließend seine eigene Konferenzverbindung beendet.

## Noch live abzunehmen

pilot.12 ist für beide Räume eingerichtet; die getrennten Ideenlisten wurden am 10. November ausgelesen. Die Aktivierung von pilot.13 benötigt noch sudo. [Gemeinsames Update und Rückweg zu pilot.12](osh-planspiel-update-vier-ideen-2026-11-10.md). Zusätzlich persönliche Ansichten, Hütchen nur in 3D und gemeinsam wartende Figuren in einer echten BBB-Konferenz prüfen.

1. Eigenen Zug ohne Präsentationsrecht durchgehend bedienen und zum nächsten Spieler wechseln.
2. Teamrotation für 2+2, 2+3, 2+2+2 und 3+3 einschließlich Phasengrenze durchspielen.
3. Alle sechs Phasen mit Überschießen, Warten, Fazitpflicht und Abschluss durchlaufen.
4. Wiedereintritt mit unveränderter und neuer Kennung sowie gezielte Neuzuordnung prüfen.
5. Export und Darstellung auf kleinen Fenstern sowie zusammen mit Audio, Video und Präsentation abnehmen.

Für die Kartensets sind die Auswahl aller sechs Ideen, dieselbe Frage bei mehreren Teilnehmenden, Wiederbeitritt und der Wechsel zur nächsten Phase noch nativ in BBB abzunehmen.

Zusätzlich für die Ideenverwaltung: Anlegen, Speichern, Wiederladen und Löschen in BBB prüfen; dieselbe Raumidee in einer neuen Konferenz wiederfinden und die Trennung zu anderen Räumen bestätigen. Der Speicherdienst muss nach einem Dienstneustart denselben Bestand laden.

## Grenzen und fachlich offene Punkte

Ein laufendes Spiel kann nicht in eine neue Konferenz importiert werden. Für den laufenden Spielstand gibt es keine dauerhafte Speicherung über das Meetingende hinweg. Die separat gespeicherten Ideenvorlagen bleiben dagegen in der JSON-Datei erhalten; ihre Sicherung gehört zur Serveradministration. Fazit-Entwürfe sind bis zum Speichern lokal. Münzwertung, automatisches Neumischen und automatische Abschlussfragen sind nicht implementiert. Die Startposition und die endgültige redaktionelle Auswahl des Kartenstapels sind offen; bei Originalkarten wird die Verwendung aller 87 Kartenpositionen ausdrücklich gewählt. Alternativ stehen zwei unveränderte individuelle Sets mit je 47 Fragen und vier zusätzliche Sets mit je 87 Fragen zur Verfügung.

Die [Würfelanimation](wuerfelanimation.md) liegt als Entwurf vor. Ihre Integration ist keine bereits ausgelieferte Funktion.

Aktuelle technische Anleitung: [Implementierungs-How-to](osh-planspiel-implementierung-howto.md). Änderungen: [Changelog](../CHANGELOG.md).
