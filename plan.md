# Plan: Multi-Agent Projekt- & Kursstruktur für den Python-Programmierkurs

## 1. Unsere Rollen im Kurs
* **KI-Agent (Lehrer):** Erklärt Konzepte anfängerfreundlich und holt mich bei meinem Bash-Wissen ab (Vergleich Bash ↔ Python), gibt kleine, leicht verdauliche Aufgaben (immer nur **1 Konzept pro Lektion**) und prüft meine Lösungen – **niemals** wird der fertige Lösungscode direkt vorweggenommen.
* **Ich (Schüler):** Ich bin Bash-Entwickler, aber Python-Anfänger, und schreibe den Code selbstständig Schritt für Schritt in den jeweiligen Lektionsordnern.

**Ziel:** Gemeinsam führen wir einen interaktiven Python-Kurs in VS Code durch, der bei meinem **Bash-Wissen** startet und kleinschrittig bis zur Entwicklung eigener **Claude Code Plugins, Hooks, CLI-Tools und MCP-Server** führt (basierend auf [ROADME.md](./ROADME.md)).

---

## 2. Der Lehrer-Skill & seine 4 Modi (`python-lehrer`)

Der Skill steuert das Verhalten des KI-Lehrers über vier klar definierte Aktionen/Befehle:

1. **`Aufgabe_Lesen`** (`/aufgabe`)
   * Zeigt an, welche Aufgabe zur aktuellen **Lektion** im aktuellen **Kapitel** gehört – **ganz ohne fertige Code-Beispiele vorzugeben**.
   * Enthält **maximal 20 % Theorie**, leicht verständlich erklärt für absolute Anfänger, gefolgt von einer klaren, kleinen Aufgabenstellung.
2. **`Frage`** (`/frage`)
   * Gibt hilfreiche Tipps, Denkanstöße und konstruktives Feedback wie ein moderner Lehrer, **ohne sofort den fertigen Code zu zeigen**.
   * *Lernregel:* Gib dir mindestens 5 Minuten für einen eigenen Versuch, bevor du fragst, und wir schauen uns dann gezielt nur die eine Stelle an, an der du feststeckst.
3. **`Loesung`** (`/loesung`)
   * Prüft deinen geschriebenen Code im aktuellen Lektionsordner, kontrolliert ob die Aufgabe richtig gelöst wurde, gibt ermutigendes Feedback und schaltet in [FORTSCHRITT.md](./FORTSCHRITT.md) zur nächsten Lektion weiter.
4. **`Aktives_Coden`** (`/aktiv` – Active Recall)
   * Code aus einem Tutorial abzutippen fühlt sich produktiv an, trainiert aber vor allem das Abschreiben. Echte Lernwirkung entsteht erst durch aktives Abrufen (*Active Recall*):
     1. Lies ein kurzes Code-Beispiel durch, bis du verstanden hast, was jede Zeile tut.
     2. Schließe das Tutorial bzw. blende das Beispiel aus.
     3. Versuche, die Lösung aus dem Gedächtnis („From Scratch“) im Lektionsordner nachzubauen.
     4. Wenn du stecken bleibst, schau kurz nach oder nutze `Frage`, schließe die Vorlage wieder und schreibe weiter.

---

## 3. Multi-Agent Skill-Architektur (Codex, Claude Code, Agy CLI & GitHub Copilot)

| KI-Tool | Basis-Regeln (Always-On) | Skill-Pfad (`SKILL.md`) | Slash-Commands / Prompts |
| :--- | :--- | :--- | :--- |
| **Antigravity CLI (`agy`)** | `AGENTS.md` / `GEMINI.md` | `.agents/skills/python-lehrer/SKILL.md` | `Aufgabe_Lesen`, `Frage`, `Loesung`, `Aktives_Coden` |
| **OpenAI Codex CLI** | `AGENTS.md` | `.agents/skills/python-lehrer/SKILL.md` | `$python-lehrer` oder direkte Modus-Nennung |
| **Claude Code** | `CLAUDE.md` | `.claude/skills/python-lehrer/SKILL.md` | `/aufgabe`, `/frage`, `/loesung`, `/aktiv` (`.claude/commands/`) |
| **GitHub Copilot (VS Code)** | `.github/copilot-instructions.md` | `.github/skills/python-lehrer/SKILL.md` | `/aufgabe`, `/frage`, `/loesung`, `/aktiv` (`.github/prompts/`) |

---

## 4. Kleinschrittige Kapitel- & Lektions-Ordnerstruktur (`kurs/`)

Damit keine Lektion zu schwer ist, ist jede Stufe (`L1`, `L2`, `L3`) in **Kapitel** unterteilt und jedes Kapitel in **kleine Einzel-Lektionen** (insgesamt 15 Kapitel mit 55 kurzen Lektionen). Alle Ordner starten leer!

```text
kurs/
├── L1_Grundlagen/                                         # 8 Kapitel, 28 kleine Anfänger-Lektionen
│   ├── Kapitel_01_Erste_Schritte_Variablen/
│   │   ├── Lektion_01_print_hallo_welt/                   # print() statt echo & Kommentare (#)
│   │   ├── Lektion_02_variablen_strings_zahlen/           # Variablen mit Typen, str & int
│   │   ├── Lektion_03_kommazahlen_rechnen/                # float & Rechnen ohne $(( )) / bc
│   │   └── Lektion_04_wahrheitswerte_vergleiche/          # bool & ==, !=, <, > statt [ ] / -eq
│   │
│   ├── Kapitel_02_Eingabe_und_Strings/
│   │   ├── Lektion_01_benutzereingabe_input/              # input() statt read & int()/str()
│   │   ├── Lektion_02_f_strings/                          # f"Hallo {name}" statt "Hallo $name"
│   │   └── Lektion_03_string_methoden/                    # .strip(), .lower(), .split() statt sed/tr/cut
│   │
│   ├── Kapitel_03_Kontrollfluss_Entscheidungen_Schleifen/
│   │   ├── Lektion_01_if_else/                            # Einfache Entscheidungen (if / else)
│   │   ├── Lektion_02_elif_und_logik/                     # elif & and, or, not statt &&, ||, !
│   │   ├── Lektion_03_for_schleife/                       # for-Schleife & range() statt seq
│   │   ├── Lektion_04_while_schleife/                     # while-Schleife, break & continue
│   │   └── Lektion_05_match_case/                         # match / case statt Bash-case
│   │
│   ├── Kapitel_04_Datenstrukturen_Sammlungen/
│   │   ├── Lektion_01_listen_grundlagen/                  # list statt Bash-Arrays, .append()
│   │   ├── Lektion_02_listen_durchlaufen_slicing/         # for über Listen & Slicing
│   │   ├── Lektion_03_tuples_unveraenderlich/             # tuple (Unveränderlichkeit)
│   │   ├── Lektion_04_dictionaries_schluessel_wert/       # dict statt declare -A
│   │   └── Lektion_05_sets_eindeutige_werte/              # set & frozenset statt sort -u
│   │
│   ├── Kapitel_05_Funktionen/
│   │   ├── Lektion_01_erste_funktion_def/                 # def statt name() { ... }
│   │   ├── Lektion_02_parameter_rueckgabe/                # Parameter statt $1/$2 & return statt echo
│   │   ├── Lektion_03_standardwerte_keyword_args/         # Default-Werte (keine mutables!)
│   │   └── Lektion_04_sichtbarkeit_scopes/                # Lokale vs. globale Variablen
│   │
│   ├── Kapitel_06_Fehlerbehandlung/
│   │   ├── Lektion_01_try_except/                         # Fehler abfangen mit try / except statt $?
│   │   └── Lektion_02_else_finally_raise/                 # else, finally (wie trap) & raise statt exit 1
│   │
│   ├── Kapitel_07_Klassen_und_Datenmodelle/
│   │   ├── Lektion_01_erste_klasse_init/                  # class, __init__, self, Attribute
│   │   ├── Lektion_02_methoden/                           # Methoden in Klassen schreiben
│   │   ├── Lektion_03_dataclasses/                        # @dataclass & frozen=True
│   │   └── Lektion_04_enums/                              # Enum für feste Auswahlwerte
│   │
│   └── Kapitel_08_Module_und_Dateien/
│       ├── Lektion_01_eigene_module_import/               # import statt source
│       └── Lektion_02_pakete_init_pathlib/                # __init__.py & pathlib.Path statt dirname/basename
│
├── L2_Fortgeschritten/                                    # 4 Kapitel, 15 Lektionen
│   ├── Kapitel_01_Kompakter_Code_Iteratoren/
│   │   ├── Lektion_01_list_dict_comprehensions/
│   │   ├── Lektion_02_generatoren_yield/
│   │   └── Lektion_03_lambda_functools/
│   ├── Kapitel_02_Typisierung_und_Qualitaet/
│   │   ├── Lektion_01_typannotationen_basis/
│   │   ├── Lektion_02_typealias_generics_newtype/
│   │   ├── Lektion_03_docstrings_und_ruff/
│   │   └── Lektion_04_typechecking_mypy_pyright/
│   ├── Kapitel_03_Projektsetup_und_Testing/
│   │   ├── Lektion_01_venv_und_uv/
│   │   ├── Lektion_02_pyproject_toml/
│   │   ├── Lektion_03_pytest_grundlagen/
│   │   └── Lektion_04_pytest_fixtures_fakes/
│   └── Kapitel_04_Moderne_Architektur_Grundlagen/
│       ├── Lektion_01_kontextmanager_with/
│       ├── Lektion_02_protocols_und_abc/
│       ├── Lektion_03_komposition_dependency_injection/
│       └── Lektion_04_factory_methoden/
│
└── L3_Profi_Plugin_Entwicklung/                           # 3 Kapitel, 12 Lektionen
    ├── Kapitel_01_Daten_Config_und_Fehler/
    │   ├── Lektion_01_json_und_tomllib/
    │   ├── Lektion_02_pydantic_validierung/
    │   ├── Lektion_03_pydantic_settings_env/
    │   └── Lektion_04_exception_hierarchien/
    ├── Kapitel_02_CLI_Logging_und_Async/
    │   ├── Lektion_01_cli_mit_typer_rich/
    │   ├── Lektion_02_logging_und_decorators/
    │   ├── Lektion_03_asyncio_grundlagen/
    │   └── Lektion_04_http_requests_httpx/
    └── Kapitel_03_Claude_Code_Plugin_Meisterkurs/
        ├── Lektion_01_clean_plugin_architektur/
        ├── Lektion_02_claude_code_hooks_python/
        ├── Lektion_03_mcp_server_python/
        └── Lektion_04_plugin_paketieren_release/
```
