# Dein strukturierter Python-Lernpfad (für Bash-Entwickler)
**Ziel:** Du kennst die Shell – jetzt lernst du Python Schritt für Schritt bis zum eigenen **Claude Code Plugin** (Moderne Python-Technik 2026). Jede Lektion holt dich bei einem Bash-Konzept ab und zeigt, wie Python es sauberer, sicherer und testbar löst.

---

## 🟢 L1 Grundlagen (Von Bash zu Python – 1 Konzept pro Lektion)

### Kapitel 01: Erste Schritte & Variablen
- **Lektion 01:** Erste Ausgabe mit `print()` statt `echo` & Kommentare (`#`, wie in Bash)
- **Lektion 02:** Variablen mit Typen (`str`, `int`) – statt `name="x"` und alles ist Text
- **Lektion 03:** Kommazahlen (`float`) & Rechnen ohne `$(( ))` und `bc` (`+`, `-`, `*`, `/`, `//`, `%`)
- **Lektion 04:** Wahrheitswerte (`bool`) & Vergleiche (`==`, `!=`, `<`, `>`) statt `[ ]`, `-eq` und Exit-Codes

### Kapitel 02: Benutzereingabe & Strings
- **Lektion 01:** Benutzereingabe (`input()` statt `read`) & Typumwandlung (`int()`, `str()`, `float()`)
- **Lektion 02:** Texte formatieren mit `f-Strings` (`f"Hallo {name}"` statt `"Hallo $name"`)
- **Lektion 03:** String-Methoden statt `sed`, `tr`, `cut` (`.strip()`, `.lower()`, `.upper()`, `.replace()`, `.split()`)

### Kapitel 03: Kontrollfluss (Entscheidungen & Schleifen)
- **Lektion 01:** Entscheidungen mit `if` und `else` (ohne `then`/`fi`, dafür Einrückung)
- **Lektion 02:** Mehrere Fälle mit `elif` & Logik (`and`, `or`, `not` statt `&&`, `||`, `!`)
- **Lektion 03:** Zählschleifen mit `for` und `range()` statt `for i in $(seq ...)`
- **Lektion 04:** Bedingte Schleifen mit `while` sowie `break` und `continue` (wie in Bash)
- **Lektion 05:** Modernes Pattern Matching (`match` / `case`) als Ersatz für Bash-`case`

### Kapitel 04: Zentrale Datenstrukturen (Sammlungen)
- **Lektion 01:** Listen (`list`) statt Bash-Arrays: erstellen, lesen, `.append()` & entfernen
- **Lektion 02:** Listen mit `for` durchlaufen & Teillisten ausschneiden (`Slicing` statt `${arr[@]:1:3}`)
- **Lektion 03:** Unveränderliche Tupel (`tuple`) – feste Daten, die Bash nicht kennt
- **Lektion 04:** Wörterbücher (`dict`) statt `declare -A` (Grundlage für JSON-Daten!)
- **Lektion 05:** Mengen (`set` & `frozenset`) statt `sort -u` für eindeutige Werte

### Kapitel 05: Funktionen & Sichtbarkeit
- **Lektion 01:** Eigene Funktionen (`def`) statt `name() { ... }`
- **Lektion 02:** Parameter statt `$1`, `$2` & echte Rückgabewerte mit `return` (statt `echo` + `$(...)`)
- **Lektion 03:** Standardwerte (`=`) & warum man niemals veränderliche Standardargumente (`=[]`) nutzt
- **Lektion 04:** Sichtbarkeit von Variablen (Lokaler vs. Globaler Scope, Vergleich mit `local`)

### Kapitel 06: Basis-Fehlerbehandlung
- **Lektion 01:** Fehler abfangen mit `try` und `except` statt `$?` und `||` (z. B. `ValueError`, `KeyError`)
- **Lektion 02:** `else`, `finally` (wie `trap`-Aufräumen) und eigene Fehler mit `raise` statt `exit 1`

### Kapitel 07: Klassen, Datenklassen & Enums
- **Lektion 01:** Erste eigene Klasse (`class`, Konstruktor `__init__`, `self` & Attribute)
- **Lektion 02:** Methoden in Klassen schreiben und aufrufen
- **Lektion 03:** Datenklassen (`@dataclass` & `@dataclass(frozen=True)`) für saubere Daten-Objekte
- **Lektion 04:** Aufzählungen (`Enum`) für feste Auswahlwerte (z. B. Event-Typen, Severity-Level)

### Kapitel 08: Module, Pakete & Dateien
- **Lektion 01:** Code auf mehrere Dateien aufteilen (`import` statt `source`)
- **Lektion 02:** Eigene Pakete (`__init__.py`) & moderner Umgang mit Dateipfaden (`pathlib.Path` statt String-Basteln mit `dirname`/`basename`)

---

## 🟡 L2 Fortgeschritten (Aus Skripten wird sauberer, getesteter & typisierter Code)

### Kapitel 01: Kompakter Code & Iteratoren
- **Lektion 01:** List- und Dict-Comprehensions (`[x for x in ...]`) statt Pipes wie `grep | sed`
- **Lektion 02:** Speicherschonende Generatoren (`yield`) – wie Pipes, die Zeile für Zeile streamen – & `itertools`
- **Lektion 03:** Anonyme Funktionen (`lambda`), Closures & `functools`

### Kapitel 02: Statische Typisierung & Code-Qualität
- **Lektion 01:** Typannotationen für Variablen und Funktionen (`int`, `str`, `list[str]`, `| None`)
- **Lektion 02:** Fortgeschrittene Typen (`TypeAlias`, Generics `class Box[T]:`, `NewType` / Value Objects)
- **Lektion 03:** Gute Docstrings schreiben & Linting/Formatting mit `ruff`
- **Lektion 04:** Statische Typprüfung mit `mypy` / `pyright`

### Kapitel 03: Projektmanagement & Testing
- **Lektion 01:** Virtuelle Umgebungen (`.venv`) & Paketmanagement mit `uv` (statt `apt`/`pip` global)
- **Lektion 02:** Projektstruktur mit `pyproject.toml`, optionalen Abhängigkeiten & `__all__`
- **Lektion 03:** Automatische Unit-Tests mit `pytest` (statt manueller Testläufe oder `bats`)
- **Lektion 04:** Testbarkeit durch `pytest` Fixtures, Fakes und Mocks

### Kapitel 04: Moderne Software-Architektur
- **Lektion 01:** Kontextmanager (`with`-Statement & `contextlib`) für sichere Ressourcenverwaltung
- **Lektion 02:** Schnittstellen definieren mit `Protocol` (Duck Typing) & `abc.ABC`
- **Lektion 03:** Komposition statt Vererbung & Dependency Injection (DI) über `__init__`
- **Lektion 04:** Factory-Methoden (`@classmethod`) für komplexe Objekterzeugung

---

## 🟠 L3 Profi (Ziel: Eigene Claude Code Plugins entwickeln)

### Kapitel 01: Validierung, Konfiguration & Fehler-Architektur
- **Lektion 01:** JSON- und TOML-Daten verarbeiten (`json`, `tomllib` statt `jq` – Basis für Hook-Input/Output)
- **Lektion 02:** Datenvalidierung & Schemas mit `pydantic` (`BaseModel`)
- **Lektion 03:** Sichere Konfiguration & `.env`-Secrets mit `pydantic-settings`
- **Lektion 04:** Strukturiertes Error Handling (Eigene Exception-Hierarchien & `raise ... from err`)

### Kapitel 02: Moderne CLI-Tools, Logging & Async
- **Lektion 01:** CLI-Tools bauen mit `typer` (oder `click`) und `rich` statt `getopts` und `case`-Parsing
- **Lektion 02:** Strukturiertes Logging (`logging`, `structlog`) & Decorators als Cross-Cutting Concern
- **Lektion 03:** Einstieg in `asyncio` (`async def`, `await`, Event Loop)
- **Lektion 04:** Asynchrone API-Aufrufe & Kontextmanager mit `httpx`

### Kapitel 03: Claude Code Plugin Meisterkurs
- **Lektion 01:** Clean Plugin Architecture: Fachlogik (Domain) strikt von CLI/Dateisystem/API trennen (ohne globalen State)
- **Lektion 02:** Eigene **Claude Code Hooks** in Python programmieren (statt Bash-Hooks: `stdin`-JSON prüfen, Exit-Codes & Entscheidungen steuern)
- **Lektion 03:** Eigenen **MCP-Server (Model Context Protocol)** in Python entwickeln und Tools bereitstellen
- **Lektion 04:** Fertiges **Claude Code Plugin** bündeln, testen und veröffentlichen (`plugin.json`, `pyproject.toml`, `uv`)
