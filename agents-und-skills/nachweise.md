# Nachweise und Grenzen des Archivs

**Erhebung:** 6. November 2026. **Bezugsstand vor dieser Ergänzung:** Dokumentationsstand vor der Archiv-Ergänzung, App `0.1.0-pilot.10`.

## Erfasster Verlauf

Ausgewertet wurden die verfügbaren Aufzeichnungen dieses Planspiel-Projektchats vom 5. und 6. November sowie vorhandene Projekt- und Prüfunterlagen. Der Verlauf belegt drei gestartete Fachagents: `board_edges`, `dice_3d` und `graphics_review`. Der Hauptagent wird zusätzlich als koordinierende Rolle beschrieben.

Für Skills sind ausgeführte Leseaufrufe der jeweiligen `SKILL.md` erfasst. Bei Bildgenerierung, PDF-Bearbeitung und Playwright lassen sich passende Werkzeugaufrufe beziehungsweise Ergebnisse zuordnen. Übrige Anleitungen bleiben als eingesehen gekennzeichnet. Die Liste verfügbarer Skills wurde nicht als Verwendungsnachweis gewertet.

## Belegarten

| Gegenstand | Grundlage | Aussagegrenze |
| --- | --- | --- |
| Drei Fachagents | Startaufrufe vom 6. November; Aufgaben- und Ergebniszusammenfassungen | Profile sind redaktionelle Zusammenfassungen, keine wörtlichen Originalaufträge |
| Neun Skill-Fassungen | Leseaufrufe vom 5.–6. November; Zeitstempel im Manifest | Lesen allein belegt keinen vollständigen Workflow |
| Imagegen | Bildwerkzeug und vorhandene Bitmap-/Prompt-Artefakte | Keine Nutzung des separat installierten CLI-Skills daraus ableiten |
| PDF | Lese-/Render-/Erstellungsabläufe und vorhandene PDFs | Nicht jeden späteren Renderlauf einer bestimmten gleichnamigen Skill-Fassung zuordnen |
| Playwright | Wrapper und CLI-Aufrufe am 5. November | Spätere CUA-Browsersteuerung ist ein anderes Werkzeug |
| Originalkopien und Quellen | Drei Skill-Hauptanleitungen mit Lizenzdateien bytegleich kopiert; Quellprüfsummen für alle neun Fassungen vom 6. November | Kein Beweis für unveränderte Installation seit dem ersten Einsatz; sechs Fassungen nur als Nutzungsprofil dokumentiert |

## Projektbelege

- [Changelog](../CHANGELOG.md): Entwicklungsschritte und damalige Prüfstände.
- [Startfehler pilot.5](../docs/osh-planspiel-startfehler-2026-11-05.md): Diagnoseergebnis und beobachtete Bestätigung.
- [Grafikupdate pilot.9](../docs/osh-planspiel-update-grafik-2026-11-06.md): Konturen, Würfel und unabhängige Grafikprüfung.
- [Verteilung-Update pilot.10](../docs/osh-planspiel-update-verteilung-2026-11-06.md): Felder, Markerprüfung und aktualisierte PDFs.
- [Quellstand und Prüfungen](../docs/quellstand-und-pruefungen.md): dokumentierte Anwendungsdateien und Prüfsummen.

Zusätzliche Messdaten, Generierungsaufträge und Browserbilder liegen in der separaten Anwendungsarbeitskopie, insbesondere unter `apps/osh-planspiel/designs/boards-3d/` und `output/playwright/osh-planspiel-pilot10/`. Rohe Chat-/Werkzeugprotokolle werden nicht in dieses Repository kopiert.

Das Archiv erfasst die in diesem ausgewerteten Verlauf nachgewiesenen Rollen und Skill-Lektüren. Es ist keine Inventur anderer BBB-Projekte oder aller installierten Skills. Nicht separat rekonstruierbare Details, etwa die genaue PDF-Skill-Fassung eines einzelnen Fachagent-Auftrags, bleiben offen.
