# Tokenverbrauch des Projekts

Stand: 2026-11-18. Alle Werte sind **Schätzungen**: deutscher Text mit Markdown ergibt etwa **3 Zeichen pro Token** (Umlaute und Sonderzeichen kosten etwas mehr als bei Englisch). Die Zahlen sind keine exakten Messwerte.

## Ergebnis auf einen Blick

**Der Tokenverbrauch ist niedrig.**

| Kennzahl | Wert |
|---|---|
| Dateien (ohne `.git`) | 29 |
| Gesamtgröße aller Textdateien | ca. 61 KB |
| Geschätzte Token, wenn man **alles** liest | ca. 20.000 |
| Fester Grundverbrauch pro Sitzung (CLAUDE.md + AGENTS.md) | ca. 1.000 Token |
| Typischer Verbrauch pro Kursaktion (Skill + Fortschritt) | ca. 2.000 bis 4.500 Token |

Zum Vergleich: Ein Kontextfenster fasst 200.000 Token oder mehr. Das gesamte Projekt belegt davon etwa 10 % und wird nie komplett geladen.

## Was wird in jeder Sitzung automatisch geladen?

| Datei | Größe | ca. Token |
|---|---|---|
| `CLAUDE.md` | 605 B | 200 |
| `AGENTS.md` (per `@`-Import in CLAUDE.md) | 2.282 B | 750 |
| Skill-Beschreibungen (nur Name und Einzeiler) | klein | ca. 300 |
| **Summe Grundverbrauch** | | **ca. 1.250** |

Der Grundverbrauch ist sehr klein und unproblematisch.

## Was kostet eine Kursaktion zusätzlich?

| Aktion | Geladene Dateien | ca. Token |
|---|---|---|
| `/aufgabe`, `/frage`, `/loesung`, `/aktiv` | Command (ca. 0,5 KB) + `python-lehrer/SKILL.md` (4,3 KB) | 1.600 |
| `/loesung` zusätzlich | `references/bewertungs_kriterien.md` (1,8 KB) | + 600 |
| Fortschritt prüfen (nur die ersten Zeilen) | `FORTSCHRITT.md`, Kopf | + 300 |
| Fortschritt komplett lesen (ganzer Baum) | `FORTSCHRITT.md` (7,4 KB, 103 Zeilen) | + 2.500 |
| `/ueberpruefen` | Command + `Ueberprüfen/SKILL.md` (2,3 KB) | 1.000 |

Dazu kommen die Antworten des Modells und der Code des Schülers. Die sind in einer Lektion sehr klein (die einzige Aufgabendatei hat 94 Bytes).

## Größte Dateien (Rangliste)

| Datei | Größe | ca. Token | Wird automatisch geladen? |
|---|---|---|---|
| `plan.md` | 9,0 KB | 3.000 | Nein |
| `FORTSCHRITT.md` | 7,4 KB | 2.500 | Nur der Kopf |
| `ROADME.md` | 6,0 KB | 2.000 | Nein |
| `README.md` | 6,0 KB | 2.000 | Nein |
| `python-lehrer/SKILL.md` | 4,3 KB | 1.400 | Nur bei Kursaktionen |
| `AGENTS.md` | 2,3 KB | 750 | Ja |

## Beobachtungen

**Gut gelöst**
- `CLAUDE.md` ist kurz und verweist nur auf andere Dateien.
- Der Hinweis, `FORTSCHRITT.md` sparsam zu lesen (nur die Zeile `Aktuelle Lektion`), spart pro Aktion rund 2.000 Token.
- Skills laden ihren Inhalt erst bei Bedarf. Im Kontext stehen vorher nur die Beschreibungen.
- Es gibt keine großen Datendateien, Logs oder Abhängigkeiten im Projekt.

**Möglichkeiten zum Sparen (gering, nicht dringend)**
1. **Dreifache Kopien:** Die Skills liegen identisch in `.claude/`, `.github/` und `.agents/` (je 4,3 KB + 1,8 KB + 2,3 KB). Das kostet **keine** zusätzlichen Token, solange man nur ein Werkzeug nutzt. Es erhöht aber den Pflegeaufwand und die Gefahr, dass die Kopien auseinanderlaufen.
2. **`FORTSCHRITT.md` wächst:** Mit jeder abgeschlossenen Lektion steigt die Größe. Bei vielen Lektionen lohnt es sich, den Fortschritt in eine kurze Statuszeile plus ein getrenntes Archiv aufzuteilen. Aktuell (103 Zeilen) ist das unkritisch.
3. **`plan.md`, `README.md`, `ROADME.md`:** Zusammen ca. 7.000 Token. Sie werden nicht automatisch geladen, es entsteht also nur Verbrauch, wenn man sie ausdrücklich liest. `ROADME.md` ist vermutlich ein Tippfehler für `ROADMAP.md` und überschneidet sich eventuell inhaltlich mit `README.md` und `plan.md`.
4. **`AGENTS.md` wird per `@`-Import immer geladen** (750 Token). Wenn die Regeln lang werden, sollten sie kurz bleiben oder in den Skill wandern.

## Fazit

Das Projekt verbraucht **wenig** Token. Der feste Grundverbrauch liegt bei ca. 1.250 Token, eine Kursaktion kostet ca. 2.000 bis 4.500 Token. Der größte künftige Kostentreiber ist das Wachstum von `FORTSCHRITT.md` und der Lektionsdateien, nicht die heutige Struktur.
