# board_edges: Brettkontur und Spielfeldgeometrie

**Kennung:** `/root/board_edges` · **Einsatz:** 6. November 2026, pilot.9 und pilot.10.

Nachträglich zusammengefasstes Aufgabenprofil; kein wörtlicher Originalauftrag.

## Auftrag

In pilot.9 sollten die Bitmap-Bretter ihre vollständige, glatte Außenkante erhalten. Die grobe, wie ausgeschnitten wirkende Kontur musste verschwinden; Brettinneres und 48 Spielfeldpositionen sollten erhalten bleiben. Zum Arbeitsbereich gehörten Kontur- und Maskengeometrie sowie die Brettdarstellung. Die Entfernung der Ansichten 4–6 wurde berücksichtigt.

In pilot.10 folgte die geometrische Prüfung der korrigierten Phase „Verteilung“: acht getrennte Felder, Fragezeichen und weißer Kreis auf eigenen Kacheln, passende Figurenpositionen und sechs gleich große Sektoren unter Berücksichtigung der Perspektive.

## Arbeitsweise und Ergebnisse

- Außenkanten und Marker in nativen Bildkoordinaten vermessen; glatte Konturmasken und passende Ausschnitte übergeben.
- Für pilot.10 Rasterbilder lesend analysieren, Messergebnisse und Ableseunsicherheit dokumentieren und gezielte Geometrietests ausführen.
- 24 Verteilungsmarker neu vermessen und einen benachbarten Werkstattmarker nachführen; bestehende Konturmasken erhalten.

Die Sektorprüfung orientierte sich an der akzeptierten Referenz. Sie ist kein Beweis mathematisch exakter Winkel in einer Rasterillustration.

Nachweise: [Grafikupdate pilot.9](../../docs/osh-planspiel-update-grafik-2026-11-06.md) und [Verteilung-Update pilot.10](../../docs/osh-planspiel-update-verteilung-2026-11-06.md).

Arbeitsdateien unter `apps/osh-planspiel/` in der separaten Anwendungsarbeitskopie: `src/board-contour.ts`, `src/bitmap-geometry.ts`, `src/board.tsx` und `designs/boards-3d/bitmap-verteilung-qa-pilot10.md` beziehungsweise `.json`.
