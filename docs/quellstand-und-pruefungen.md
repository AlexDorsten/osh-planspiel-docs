# Quellstand und Prüfungen

Stand: **10. November 2026** · lokal geprüfte App **0.1.0-pilot.13**, SDK **1.0.0-beta.3**, Ereignisprotokoll **3** (Originalhistorien mit Protokoll 2 lesbar). Serveraktivierung und native Abnahme dieser Fassung noch offen. pilot.12 ist bereits für beide Räume eingerichtet.

Die Anwendungsarbeitskopie hat keine eigene Git-Revision. Die SHA-256-Werte bezeichnen die geprüften Quellen relativ zu `apps/osh-planspiel/`; ausführbare Quellen und Installationspakete liegen außerhalb dieses Dokumentationsrepos.

| Datei | SHA-256 |
| --- | --- |
| `package.json` | `c907130ec689c671f0b27bbf8be14e31a95a92d0423ae1ebf8f333b5c63e5e54` |
| `package-lock.json` | `74fccd3c7f45e75d0572000a580db30fc2f51ae304935488b27f6055404408b0` |
| `src/plugin.tsx` | `e0924bd35b32505df1d5c00fa4dc40c4b7676384d475e9f97281e1a22201cdca` |
| `src/model.ts` | `3c6eff77bd7afb56ef82b47a46b673b122aca0be431eb2752cf5799b2c3bdd3a` |
| `src/store.ts` | `99e7c226d54041092650563759fd17233d1665c97847b7d168829b0edb3db6be` |
| `src/participants.ts` | `cd2b3a3176409319f150d48228502024fabc2ba6c50be057aa2d983623efc18f` |
| `src/random.ts` | `b6cee0a1db69749c07fb033e83b13ad9a1205912474ea3c5570eb2e6f47b8217` |
| `src/app.tsx` | `92c13c6bd97903567904f910b360839fe504ea3558027c1bc968d25ac75dd79c` |
| `src/board.tsx` | `6ced95cbfba17dd6f57db97ad471572996b0e6d127276c310fea32f520d3bdc8` |
| `src/board-geometry.ts` | `1bf04de137d581bf171db737caf1a185d34a45217d351c8ad6e7f44e399ad4ef` |
| `src/bitmap-geometry.ts` | `411e1f0d4e1ed04a54e8063cfa37d603cec65e6b8ce7316196d1d7348c7d56df` |
| `src/views.ts` | `84396e70603c9acce35855b0ce893802c1471503277ab6c005299e0f5c7b7b95` |
| `src/table-accessories.tsx` | `0affd5bd0eb9e3bd292660f1f4be6f641a575b7a620286661c2019b9278e6121` |
| `src/styles.css` | `b2bd6f03608090a38c02088c2df08f7c429ed01f1044a3a53289297b0e61b826` |
| `tests/views.test.ts` | `b233391e7a81bb78322c0e86e63475ed867cd1eedbe0d61411e8a8c6482fd318` |
| `scripts/build.mjs` | `240be851010baa76a1531d390d01920b716429b7c50ad0e198855791a78dfa6c` |
| `scripts/package.mjs` | `bde2da8fc585a6680194347ec6fd913f8ea50a45fb9284d6c521b676e3992cc3` |
| `scripts/fixture.mjs` | `9c80e4ff7f26ffa3e2a4b026f40caba5638656cabcdd30b371841048eb8ab0db` |
| `deploy/install.py` | `1da9ef8bb144068f2c471f2fe6087e1594d4f960dd59cfaf4341f99b83104aad` |
| `deploy/room.rb` | `b50e6b1f29f8d43958a8a35818377b4efd0078740b00d86ad46f533fcf6c1610` |
| `src/board-contour.ts` | `daf6af43c95acce811fc9307ff2aba17e91643d12379c56a0cc21e090b71dcf0` |
| `src/die.tsx` | `9cccd4848b339dc69405dfb063a2f618287ed713544fb648d28928e56259483e` |
| `tests/die.test.ts` | `eb6f2ae4b6714650cc9ef9273212747c88e9b794b5225ac24598139078f9baf2` |
| `scripts/graphics-review.tsx` | `80ea5c192fc8f713474d4972d538e62df3195325ed76fcf1ab5e87010d6eda84` |
| `content/board.de.json` | `20cd7970429687a9dbd28960dee4d5e403a023cbc7774d3d162bf03b14cc0180` |
| `tests/board-content.test.ts` | `4786bc0783f07a0b126c4e81e1567334bee55cf1c584dfdda957f8bfa39f25f8` |
| `tools/prepare_materials.py` | `e8b3066225bbe308c2225534ab4fadd886d9cf7ce509079ffb760394dbad7c84` |
| `tools/build_board_designs.py` | `8c7b35f684859ba48896681b63ed3e8bc6869c388b451671ae8d78cc339d23e8` |
| `tools/build_player_guide.py` | `a807ee2b6f1df9809c2da2798ec8e0688879a665c67b1797d375c50620a35dfd` |
| `designs/boards-3d/3d-tischmodell.png` | `dece99a78f769044d8f2de5abf9074641462b1b1973c3a38e0a566f2f7585cfb` |
| `designs/boards-3d/3d-werkstatt.png` | `d69c8605624929d46a293b23fecc9dff9d39eb084ce444caa7dbab40c6e74a99` |
| `designs/boards-3d/3d-spiellandschaft.png` | `57d74e3d35f321ad2c1c31591a03d013be915280fe91e8ce5bc9b7690472db35` |
| `designs/boards-v1/spielplan-klar.svg` | `5b24eaae531f897ede85c98f19a6fa7c33eb7dc3dc55f2628c8c201767c517ac` |
| `designs/boards-v1/spielplan-werkstatt.svg` | `544ad5e55e4f627b30a5f96c4accf2f3fff66b3550f1501167876be56b7551da` |
| `designs/boards-v1/spielplan-dialog.svg` | `8e2d5677f9c3e4d1578ee6c6cc702c1d7a52654620c786b49ce3bd9ae768cc5d` |
| `designs/boards-3d/verteilung-imagegen-prompts.json` | `6f04849684b2f036ca0a822ed25e5cbbf352eaef8edf1ac08a3952d3b1cc8594` |
| `designs/boards-3d/bitmap-verteilung-qa-pilot10.md` | `29f3cd103c41741c46ac2e1dbcaf055c258c773d0388bf808e895ec121253f97` |
| `designs/boards-3d/bitmap-verteilung-qa-pilot10.json` | `75e3123d5672a9a239fabb552911bb9eaec02b6728ae7fb3623dad4ca01ae713` |
| `src/ideas.ts` | `473b8ac34c215a9320c14ab71062913d8167ed3c0ec03c15cd6c6e4486d94386` |
| `src/idea-editor.tsx` | `5840da52c4d1b66d640c35fef06cf60e4f81fa2ffc9f7ba6784dfc2fde2e4e7a` |
| `content/default-idea.de.json` | `b8a01abed3c25b5b68584ba0a4bad78d69faffd6d8e72f6f02a4ddfd93d43c15` |
| `server/ideas.py` | `5a889f386afe62757140f2555c3c621aad80bafae091b84c4dfbd4476e70ed20` |
| `deploy/install-ideas.py` | `d998b10fe498d2f654c12d6e514d62a886b32350bd3cd35db604752b0da0a339` |
| `deploy/ideas-config.json` | `e3ee1d74a691542b734aa7f1a0e6c81461d36f5b7bc770ec6355ba2eb6d39ff0` |
| `deploy/osh-planspiel-ideas.service` | `10109478702145be48616a799840e7f094f2ac2ff79360bb47a0ac79bf73328b` |
| `deploy/osh-planspiel-ideas.nginx` | `37208deee609bdc444d7304a0d5ecf212c7439e0ea7255ebaab43f4b2151c31a` |
| `tests/ideas.test.ts` | `258e715693693035b75cf8b60c88563adf1039f3d747821030e6ed9c1db34060` |
| `tests/ideas_test.py` | `77d2ea9a22ec36b1d8a39c70288e5966754f6356e90070b8af4dbda4f357916c` |
| `tests/install_test.py` | `9843b242ba0ea909763c77273665c82d319d6b2cd27819f783fb363d925b0249` |
| `src/card-sets.ts` | `7e7e93fd72c69ff1bab431a38f9075dd087f5551aa7526464499eb85ef94c015` |
| `content/personalized/modular-openshelf-v1.de.json` | `7a80d04cc16cb7d227190f7d9b78bfdea28a1cec33d2f2bfaee78c15c551124f` |
| `content/personalized/uniprokit-maxi-v1.de.json` | `652a60024ebc3263a1279401760ba3795a8421f043a861539b68de82e9294058` |
| `tests/card-sets.test.ts` | `1fcbb3c31e155c9e028e20cc161aaa0b0b533cd124db480be42fb43f518cd71a` |
| `deploy/update-rooms.py` | `6efb8bda0d4140ce0c8833bcb4270cf07cf1ed62e97e2c52e0bfe70b905d3886` |
| `deploy/update-rooms.rb` | `1ef0d0d83cde87ac9642fd8115bb52254bb0cc3ed7f01d758abacd483f11fbe8` |
| `deploy/read-ideas-for-cards.py` | `fa74c0fa3a718a762a0bb6d6a77cdd469569edf363bb28e042d034c03c46bac2` |
| `tests/update_rooms_test.py` | `a4440f77c7a57faa95233bc2b38269a28d158fcefbc74740c583aaa40acc0c40` |
| `tests/update_rooms_test.rb` | `03c82dd84eff71537a05eaad54d9c29838364e019d20bfcab0ca32ee951697fb` |
| `content/personalized/usb-c-werkzeug-akku-v1.de.json` | `c8f5fc5fe8e2c0afa19225c184169b18c0656ee29945709d56117288d456b1e5` |
| `content/personalized/kindergarten-laubkompost-v1.de.json` | `b767f9a4323f708c3ca6a8333c285a176533a204189c9d5f0ed349130f6f2405` |
| `content/personalized/oseg-ideenplattform-v1.de.json` | `d096f75643e73a8b6e77ca3d7fafa9ce1216a0dab0f925a1b23c8d022f155dde` |
| `content/personalized/unidockit-v1.de.json` | `aceb15c7743e345d2b557210a2ca6dffd6c8bbce2dcaa86bd1bd8c58b1a89836` |

## Ausgeführte Prüfungen

| Prüfung | Ergebnis |
| --- | --- |
| `npm run typecheck` | erfolgreich |
| TypeScript-Tests | 44 bestanden |
| Build / Paket | erfolgreich; zwölf statische Assets, sechs individuelle Sets |
| Installertests Python | sechs bestanden |
| Zwei-Raum-Updatetests Python | sechs bestanden |
| Zwei-Raum-Plan Ruby | vier Tests, 15 Assertions, keine Fehler |
| Kartendaten | viermal 87, zweimal unverändert 47; korrekte Phasen und Rollen; alle 348 neuen Fragen verschieden |
| Alte Sets | OpenShelf und Maxi per festem SHA-256 bytegleich bestätigt |
| Spielmodell | vollständiger Verbrauch aller sechs Sets ohne Wiederholung oder fremde Phase; gemeinsame Wiederherstellung |
| Browser | sechs Vorauswahlen, 87er-Spielstart, passende UniDocKit-Frage, später Beitritt, Neuladen, unabhängiger zweiter Testraum |
| Darstellung | Kartenauswahl breit und bei 620 Pixeln geprüft |
| Serverbereitstellung | drei Paketdateien per SHA-256 bestätigt; zwölf Rückwegdateien auf Disk und über HTTPS geprüft; sudo verlangt Passwort |
| Paketprüfung | eingebetteter Zwei-Raum-Runner und alle Assets stimmen mit Build überein; zwölf Rückweg-Hashes entsprechen archivierter pilot.12 |

Die Speicherkomponente bleibt unverändert; ihre sechs Speicher-/HTTP-Tests wurden zuletzt mit pilot.11 ausgeführt. Grafiknachweise bleiben in den Änderungsblättern pilot.9/pilot.10 erhalten. Die Bedienungs-PDF pilot.12 bleibt als ausdrücklich älterer Stand erhalten; die aktuelle Markdown-Anleitung beschreibt die sechs Sets.

Die native BBB-Abnahme des neuen Releases bleibt offen. Der lokale Prüfstand simuliert BBB und ersetzt keine vollständige Live-Abnahme.

[Neue Karten und Aktivierung](osh-planspiel-update-vier-ideen-2026-11-10.md) · [Stand und Abnahme](stand-und-abnahme.md).
