# Skill-Katalog

Stand: **6. November 2026**. Erfasst sind neun im ausgewerteten Projektverlauf gelesene Skill-Fassungen. **Eingesetzt** bedeutet, dass neben der Lektüre passende Werkzeugaufrufe oder Ergebnisse nachweisbar sind; es bescheinigt keine vollständige Prüfung aller Skill-Vorgaben.

| Skill-Fassung | Status | Verwendung im Projekt | Dokumentation |
| --- | --- | --- | --- |
| `imagegen` – integrierter System-Skill | Eingesetzt | Bitmap-Entwürfe, Tischszenen und Bildkorrekturen der 3D-Spielpläne über das integrierte Bildwerkzeug | [SKILL.md](imagegen/SKILL.md) |
| `pdf:pdf` – Runtime-Paket `26.1103.10131` | Eingesetzt | Spielmaterial lesen, Karten-/Spielplanentwürfe und Betreiberanleitung erstellen und visuell prüfen | [Nutzungsprofil](pdf-runtime/README.md) |
| `pdf` – lokale Installation | Eingesetzt | Weitere PDF-Erstellung und Prüfung, insbesondere Betreiber- und Online-Bedienungsanleitung | [SKILL.md](pdf-local/SKILL.md) |
| `playwright` – lokale Installation | Eingesetzt | Browserprüfungen der BBB-Einbindung und Bedienabläufe am 5. November; Wrapper und CLI tatsächlich aufgerufen | [SKILL.md](playwright/SKILL.md) |
| `diagnose` | Eingesehen | Bei Bedien- und Spielstartfehlern konsultiert; auch vor der Grafikkorrektur gelesen. Vollständige Skill-Anwendung nicht nachgewiesen | [Nutzungsprofil](diagnose/README.md) |
| `setup-matt-pocock-skills` | Eingesehen | Als Voraussetzung zu `diagnose` geprüft. Daraus erzeugte Projektkonfiguration nicht nachgewiesen | [Nutzungsprofil](setup-matt-pocock-skills/README.md) |
| `prototype` | Eingesehen | Bei der Sichtung von Karten und Spielmaterial gelesen. Nach dessen Branch-Anleitung erstellter Wegwerfprototyp nicht nachgewiesen | [Nutzungsprofil](prototype/README.md) |
| `documents:documents` – Runtime-Paket `26.1103.10131` | Eingesehen | Für die Betreiberanleitung geprüft. Zugehöriger DOCX-Erstellungs-/Renderlauf nicht nachgewiesen; geliefert wurde eine PDF | [Nutzungsprofil](documents/README.md) |
| `pages:write-page` – Paket `0.1.26` | Eingesehen | Bei der Wahl des Dokumentationsformats geprüft. Damit gespeicherte ChatGPT Page nicht nachgewiesen | [Nutzungsprofil](write-page/README.md) |

## Herkunft und Umfang

Installationspfade, Lesezeitpunkte, Archivdatum und SHA-256-Prüfsummen stehen im [Manifest](../manifest.json). Benutzerverzeichnisse werden als `~` dargestellt. Die beiden PDF-Fassungen bleiben wegen unterschiedlicher Herkunft und Inhalte getrennt. Der zusätzlich verfügbare lokale Imagegen-CLI-Skill ist nicht als verwendet belegt und daher nicht aufgenommen.

Originalanleitungen von `imagegen`, lokalem `pdf` und `playwright` sind samt ihrer mitgelieferten Apache-Lizenz und vorhandener `NOTICE.txt` unverändert archiviert. Die übrigen sechs Ordner enthalten eigene Nutzungsprofile mit Herkunft und SHA-256 der Hauptanleitung. Das Documents-Paket untersagt externe dauerhafte Kopien ausdrücklich; für die anderen fünf Fassungen wurde keine mitgelieferte Weitergabefreigabe erfasst. Deshalb sind ihre Originaltexte nicht kopiert.

Die Anleitungen können Skripte, externe Ressourcen und Umgebungen voraussetzen, die dieses Dokumentationsrepo nicht mitliefert. Ein kopierter Ordner allein ist kein vollständiges ausführbares Skill-Paket.

## Werkzeuge sind keine zusätzlichen Skills

Browsersteuerung über `mcp__cua_repl`, das integrierte Bildwerkzeug, Git/GitHub, ReportLab, Poppler und TypeScript-Prüfwerkzeuge waren ebenfalls beteiligt. Sie werden nicht als zusätzliche `SKILL.md` gezählt. Ein Screenshot unter `output/playwright/` allein beweist keinen Playwright-Skill-Einsatz; hier ist dessen frühere Nutzung durch CLI-Aufrufe belegt.

Weitere Details: [Nachweise und Grenzen](../nachweise.md).

## Weitere nachgewiesene Einsätze

- **13. November 2026 – lokaler PDF-Skill:** Original-PDFs aus Zenodo-Eintrag 17811561 mit `pdftotext` auf Herkunfts- und Lizenzangaben geprüft, mit Poppler gerendert und visuell gesichtet. Die Originaldateien blieben unverändert. Die verwendete `SKILL.md` stimmt mit der archivierten Fassung überein; der Einsatz ist im [Manifest](../manifest.json) ergänzt.

- **14. November 2026 – lokaler PDF-Skill:** Vier Bedienungs-PDFs um die tatsächliche Konferenzbezeichnung bereinigt; Inhalte tatsächlich entfernt, Ersatztext eingefügt, Seiten gerendert und geprüft. Zenodo-Originale unverändert.
