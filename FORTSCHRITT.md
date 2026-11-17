# Lernfortschritt – Python-Kurs (Ziel: Eigene Claude Code Plugins)

> **Hinweis für KI-Agenten:** Lies diese Datei zu Beginn jeder Sitzung, um zu wissen, in welchem Kapitel und in welcher Lektion der Schüler gerade arbeitet. Jede Lektion behandelt **nur ein einzelnes, anfängerfreundliches Thema**. Aktualisiere den Status, sobald eine Lektion über `Loesung` erfolgreich abgeschlossen wurde.

**Aktuelle Lektion:** `kurs/L1_Grundlagen/Kapitel_01_Erste_Schritte_Variablen/Lektion_01_print_hallo_welt`

---

## 🟢 L1 Grundlagen (Anfänger – Schritt für Schritt)

### Kapitel 01: Erste Schritte & Variablen (`Kapitel_01_Erste_Schritte_Variablen`)
- [ ] `Lektion_01_print_hallo_welt` – Erste Ausgabe mit `print()` & Kommentare (`#`)
- [ ] `Lektion_02_variablen_strings_zahlen` – Variablen anlegen, Text (`str`) und Ganze Zahlen (`int`)
- [ ] `Lektion_03_kommazahlen_rechnen` – Kommazahlen (`float`) & Grundrechenarten (`+`, `-`, `*`, `/`, `//`, `%`)
- [ ] `Lektion_04_wahrheitswerte_vergleiche` – Wahrheitswerte (`bool`: `True`/`False`) & Vergleiche (`==`, `!=`, `<`, `>`)

### Kapitel 02: Benutzereingabe & Strings (`Kapitel_02_Eingabe_und_Strings`)
- [ ] `Lektion_01_benutzereingabe_input` – Benutzereingabe (`input()`) & Typumwandlung (`int()`, `str()`, `float()`)
- [ ] `Lektion_02_f_strings` – Texte elegant formatieren mit `f-Strings` (`f"..."`)
- [ ] `Lektion_03_string_methoden` – Wichtige String-Methoden (`.strip()`, `.lower()`, `.upper()`, `.replace()`, `.split()`)

### Kapitel 03: Kontrollfluss (`Kapitel_03_Kontrollfluss_Entscheidungen_Schleifen`)
- [ ] `Lektion_01_if_else` – Einfache Entscheidungen treffen mit `if` und `else`
- [ ] `Lektion_02_elif_und_logik` – Mehrere Fälle prüfen mit `elif` & Logik (`and`, `or`, `not`)
- [ ] `Lektion_03_for_schleife` – Zählschleifen mit `for` und `range()`
- [ ] `Lektion_04_while_schleife` – Bedingte Schleifen mit `while` sowie `break` und `continue`
- [ ] `Lektion_05_match_case` – Modernes Pattern Matching (`match` / `case` ab Python 3.10+)

### Kapitel 04: Datenstrukturen (`Kapitel_04_Datenstrukturen_Sammlungen`)
- [ ] `Lektion_01_listen_grundlagen` – Listen (`list`) erstellen, Elemente lesen, `.append()` & entfernen
- [ ] `Lektion_02_listen_durchlaufen_slicing` – Listen mit `for` durchlaufen & Teillisten (`Slicing`)
- [ ] `Lektion_03_tuples_unveraenderlich` – Unveränderliche Tupel (`tuple`)
- [ ] `Lektion_04_dictionaries_schluessel_wert` – Wörterbücher (`dict`) mit Schlüssel-Wert-Paaren
- [ ] `Lektion_05_sets_eindeutige_werte` – Mengen (`set` & `frozenset`) für eindeutige Werte

### Kapitel 05: Funktionen (`Kapitel_05_Funktionen`)
- [ ] `Lektion_01_erste_funktion_def` – Eigene Funktionen schreiben (`def`) und aufrufen
- [ ] `Lektion_02_parameter_rueckgabe` – Parameter übergeben und Ergebnisse mit `return` zurückgeben
- [ ] `Lektion_03_standardwerte_keyword_args` – Standardwerte (`=`) & veränderliche Standardargumente vermeiden
- [ ] `Lektion_04_sichtbarkeit_scopes` – Sichtbarkeit von Variablen (Lokaler vs. Globaler Scope)

### Kapitel 06: Basis-Fehlerbehandlung (`Kapitel_06_Fehlerbehandlung`)
- [ ] `Lektion_01_try_except` – Programmabstürze abfangen mit `try` und `except`
- [ ] `Lektion_02_else_finally_raise` – `else`, `finally` und eigene Fehler auslösen mit `raise`

### Kapitel 07: Klassen & Datenmodelle (`Kapitel_07_Klassen_und_Datenmodelle`)
- [ ] `Lektion_01_erste_klasse_init` – Erste eigene Klasse (`class`, `__init__`, `self` & Attribute)
- [ ] `Lektion_02_methoden` – Methoden in Klassen schreiben und aufrufen
- [ ] `Lektion_03_dataclasses` – Datenklassen (`@dataclass` & `@dataclass(frozen=True)`)
- [ ] `Lektion_04_enums` – Aufzählungen (`Enum`) für feste Auswahlwerte

### Kapitel 08: Module & Dateien (`Kapitel_08_Module_und_Dateien`)
- [ ] `Lektion_01_eigene_module_import` – Code auf mehrere Dateien aufteilen (`import`, `from ... import`)
- [ ] `Lektion_02_pakete_init_pathlib` – Eigene Pakete (`__init__.py`) & Dateipfade (`pathlib.Path`)

---

## 🟡 L2 Fortgeschritten

### Kapitel 01: Kompakter Code & Iteratoren (`Kapitel_01_Kompakter_Code_Iteratoren`)
- [ ] `Lektion_01_list_dict_comprehensions` – List- und Dict-Comprehensions (`[x for x in ...]`)
- [ ] `Lektion_02_generatoren_yield` – Speicherschonende Generatoren (`yield`) & `itertools`
- [ ] `Lektion_03_lambda_functools` – Anonyme Funktionen (`lambda`), Closures & `functools`

### Kapitel 02: Typisierung & Qualität (`Kapitel_02_Typisierung_und_Qualitaet`)
- [ ] `Lektion_01_typannotationen_basis` – Typannotationen für Variablen und Funktionen (`int`, `str`, `| None`)
- [ ] `Lektion_02_typealias_generics_newtype` – `TypeAlias`, Generics (`class Box[T]:`), `NewType` & Value Objects
- [ ] `Lektion_03_docstrings_und_ruff` – Docstrings schreiben & Linting/Formatting mit `ruff`
- [ ] `Lektion_04_typechecking_mypy_pyright` – Statische Typprüfung mit `mypy` / `pyright`

### Kapitel 03: Projektsetup & Testing (`Kapitel_03_Projektsetup_und_Testing`)
- [ ] `Lektion_01_venv_und_uv` – Virtuelle Umgebungen (`.venv`) & Paketmanagement mit `uv`
- [ ] `Lektion_02_pyproject_toml` – `pyproject.toml`, optionale Abhängigkeiten & `__all__`
- [ ] `Lektion_03_pytest_grundlagen` – Automatische Unit-Tests schreiben mit `pytest`
- [ ] `Lektion_04_pytest_fixtures_fakes` – Testbarkeit durch `pytest` Fixtures, Fakes und Mocks

### Kapitel 04: Moderne Architektur (`Kapitel_04_Moderne_Architektur_Grundlagen`)
- [ ] `Lektion_01_kontextmanager_with` – Kontextmanager (`with`-Statement & `contextlib`)
- [ ] `Lektion_02_protocols_und_abc` – Schnittstellen definieren mit `Protocol` & `abc.ABC`
- [ ] `Lektion_03_komposition_dependency_injection` – Komposition statt Vererbung & Dependency Injection (`__init__`)
- [ ] `Lektion_04_factory_methoden` – Factory-Methoden (`@classmethod`) für komplexe Konstruktion

---

## 🟠 L3 Profi (Plugin-Entwicklung)

### Kapitel 01: Daten, Config & Fehler (`Kapitel_01_Daten_Config_und_Fehler`)
- [ ] `Lektion_01_json_und_tomllib` – JSON- und TOML-Daten verarbeiten (`json`, `tomllib`)
- [ ] `Lektion_02_pydantic_validierung` – Datenvalidierung & Schemas mit `pydantic` (`BaseModel`)
- [ ] `Lektion_03_pydantic_settings_env` – Sichere Konfiguration & `.env`-Secrets mit `pydantic-settings`
- [ ] `Lektion_04_exception_hierarchien` – Eigene Exception-Hierarchien & Exception Chaining (`raise ... from err`)

### Kapitel 02: CLI, Logging & Async (`Kapitel_02_CLI_Logging_und_Async`)
- [ ] `Lektion_01_cli_mit_typer_rich` – Moderne CLI-Anwendungen bauen mit `typer` und `rich`
- [ ] `Lektion_02_logging_und_decorators` – Strukturiertes Logging (`logging`, `structlog`) & Decorators
- [ ] `Lektion_03_asyncio_grundlagen` – Einstieg in `asyncio` (`async def`, `await`, Event Loop)
- [ ] `Lektion_04_http_requests_httpx` – Asynchrone API-Aufrufe mit `httpx`

### Kapitel 03: Claude Code Plugin Meisterkurs (`Kapitel_03_Claude_Code_Plugin_Meisterkurs`)
- [ ] `Lektion_01_clean_plugin_architektur` – Clean Architecture: Domain strikt von CLI/Dateisystem/API trennen
- [ ] `Lektion_02_claude_code_hooks_python` – Eigene Claude Code Hooks in Python entwickeln
- [ ] `Lektion_03_mcp_server_python` – Eigenen MCP-Server in Python entwickeln
- [ ] `Lektion_04_plugin_paketieren_release` – Fertiges Claude Code Plugin bündeln & veröffentlichen (`uv`, `plugin.json`)
