# Agents und Skills im OSH-Planspiel

Stand: **6. November 2026**, Projektstand **0.1.0-pilot.10**.

Dieses Archiv dokumentiert die bisher nachweisbaren Agent-Rollen und Skill-Anleitungen der Planspiel-Entwicklung: vier Rollenprofile sowie neun Skill-Fassungen mit Herkunft und Nutzungsnachweis. Zwei Fassungen gehören zum gleichnamigen PDF-Skill.

## Agent-Rollen

| Agent | Aufgabe |
| --- | --- |
| [Hauptagent `/root`](agents/hauptagent.md) | Umsetzung, Integration, BBB-Anbindung, Dokumentation und Gesamtprüfung |
| [`board_edges`](agents/board_edges.md) | Brettkonturen, Markerpositionen und geometrische Prüfung der Bitmap-Spielpläne |
| [`dice_3d`](agents/dice_3d.md) | Räumlicher Würfel; später auch 2D-Spielpläne und PDF-Aktualisierung |
| [`graphics_review`](agents/graphics_review.md) | Unabhängige visuelle Prüfung von Brettern, Würfel und Figuren |

Die drei Fachagents wurden für die vom Nutzer gewünschte gemeinsame Grafiküberarbeitung eingesetzt. Die Profile fassen ihre Aufgaben und Ergebnisse zusammen. Sie sind keine wörtlichen Originalprompts und keine exportierten Laufzeitkonfigurationen. Eine separate Modellwahl ist nicht dokumentiert.

## Skill-Archiv

Der [Skill-Katalog](skills/README.md) unterscheidet **eingesetzt** und **eingesehen**. Ein gelesener Skill allein beweist nicht, dass sein gesamter Ablauf ausgeführt wurde. Auch die nur konsultierten Anleitungen bleiben nachvollziehbar erhalten.

Bei `imagegen`, lokalem `pdf` und `playwright` sind die am Archivdatum vorhandenen `SKILL.md` samt mitgelieferter Apache-Lizenz und vorhandenen Hinweisen unverändert archiviert. Die sechs übrigen Fassungen sind als eigene Nutzungsprofile mit Herkunft und Prüfsumme dokumentiert. Das Documents-Paket untersagt externe dauerhafte Kopien ausdrücklich; bei den übrigen fünf Fassungen wird keine Weitergabefreigabe behauptet. Skripte und Laufzeitpakete sind nicht enthalten. Dies ist ein Dokumentationsarchiv, kein vollständiges Installationspaket.

[Nachweise und Grenzen](nachweise.md) erklären die Zuordnung. Das [Manifest](manifest.json) enthält Quelldateien, Zeitpunkte der nachgewiesenen Skill-Lektüre und SHA-256-Prüfsummen. Die Prüfsummen identifizieren die vorhandenen Quellfassungen und, soweit übernommen, ihre Kopien vom Archivdatum; sie behaupten keine unveränderte historische Fassung seit dem ersten Einsatz.

## Wiederverwenden und pflegen

1. Rollenprofil und projektspezifische Verwendung im Skill-Katalog lesen.
2. Für eine erneute Ausführung den vollständigen Skill aus seiner ursprünglichen Installation bereitstellen und dessen aktuelle Voraussetzungen prüfen.
3. Neue Einsätze mit Datum, Aufgabe und Ergebnis ergänzen; neue Skill-Versionen als eigenen Archivstand festhalten.
4. Manifest, Katalog und [Changelog](../CHANGELOG.md) gemeinsam pflegen.

Die Ablage aktiviert keine Agent-Konfiguration. Ursprüngliche Lizenz- und Urheberhinweise der Skills bleiben erhalten. Die am 13. November 2026 dokumentierte [CC-BY-4.0-Lizenz des Zenodo-Spielmaterials](../LIZENZ.md) ändert die Lizenzen dieser fremden Skill-Texte nicht.
