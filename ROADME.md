# Python-Lernpfad Roadmap (Anfängerfreundlich: Kapitel & Einzel-Lektionen)
**Ziel:** Schritt für Schritt von Null bis zum eigenen **Claude Code Plugin** (Moderne Python-Technik 2026)

---

## 🟢 L1 Grundlagen (Für absolute Anfänger – 1 Konzept pro Lektion)

### Kapitel 01: Erste Schritte & Variablen
- **Lektion 01:** Erste Ausgabe mit `print()` & Kommentare (`#`)
- **Lektion 02:** Variablen anlegen, Text (`str`) und Ganze Zahlen (`int`)
- **Lektion 03:** Kommazahlen (`float`) & Grundrechenarten (`+`, `-`, `*`, `/`, `//`, `%`)
- **Lektion 04:** Wahrheitswerte (`bool`: `True`/`False`) & Vergleiche (`==`, `!=`, `<`, `>`)

### Kapitel 02: Benutzereingabe & Strings
- **Lektion 01:** Benutzereingabe (`input()`) & Typumwandlung (`int()`, `str()`, `float()`)
- **Lektion 02:** Texte elegant formatieren mit `f-Strings` (`f"Hallo {name}"`)
- **Lektion 03:** Wichtige String-Methoden (`.strip()`, `.lower()`, `.upper()`, `.replace()`, `.split()`)

### Kapitel 03: Kontrollfluss (Entscheidungen & Schleifen)
- **Lektion 01:** Einfache Entscheidungen treffen mit `if` und `else`
- **Lektion 02:** Mehrere Fälle prüfen mit `elif` & Logik (`and`, `or`, `not`)
- **Lektion 03:** Zählschleifen mit `for` und `range()`
- **Lektion 04:** Bedingte Schleifen mit `while` sowie `break` und `continue`
- **Lektion 05:** Modernes Pattern Matching (`match` / `case` ab Python 3.10+)

### Kapitel 04: Zentrale Datenstrukturen (Sammlungen)
- **Lektion 01:** Listen (`list`) erstellen, Elemente lesen, hinzufügen (`.append()`) & entfernen
- **Lektion 02:** Listen mit `for` durchlaufen & Teillisten ausschneiden (`Slicing`)
- **Lektion 03:** Unveränderliche Tupel (`tuple`) – warum feste Daten sicherer sind
- **Lektion 04:** Wörterbücher (`dict`) mit Schlüssel-Wert-Paaren (Grundlage für JSON-Daten!)
- **Lektion 05:** Mengen (`set` & `frozenset`) für eindeutige Werte ohne Duplikate

### Kapitel 05: Funktionen & Sichtbarkeit
- **Lektion 01:** Eigene Funktionen schreiben (`def`) und aufrufen
- **Lektion 02:** Parameter übergeben und Ergebnisse mit `return` zurückgeben
- **Lektion 03:** Standardwerte (`=`) & warum man niemals veränderliche Standardargumente (`=[]`) nutzt
- **Lektion 04:** Sichtbarkeit von Variablen (Lokaler vs. Globaler Scope)

### Kapitel 06: Basis-Fehlerbehandlung
- **Lektion 01:** Programmabstürze abfangen mit `try` und `except` (z. B. `ValueError`, `KeyError`)
- **Lektion 02:** `else`, `finally` und eigene Fehler gezielt auslösen mit `raise`

### Kapitel 07: Klassen, Datenklassen & Enums
- **Lektion 01:** Erste eigene Klasse (`class`, Konstruktor `__init__`, `self` & Attribute)
- **Lektion 02:** Methoden in Klassen schreiben und aufrufen
- **Lektion 03:** Datenklassen (`@dataclass` & `@dataclass(frozen=True)`) für saubere Daten-Objekte
- **Lektion 04:** Aufzählungen (`Enum`) für feste Auswahlwerte (z. B. Event-Typen, Severity-Level)

### Kapitel 08: Module, Pakete & Dateien
- **Lektion 01:** Code auf mehrere Dateien aufteilen (`import`, `from ... import`)
- **Lektion 02:** Eigene Pakete (`__init__.py`) & moderner Umgang mit Dateipfaden (`pathlib.Path`)

---

## 🟡 L2 Fortgeschritten (Sauberer, getesteter & typisierter Code)

### Kapitel 01: Kompakter Code & Iteratoren
- **Lektion 01:** List- und Dict-Comprehensions (`[x for x in ...]`)
- **Lektion 02:** Speicherschonende Generatoren (`yield`) & `itertools`
- **Lektion 03:** Anonyme Funktionen (`lambda`), Closures & `functools`

### Kapitel 02: Statische Typisierung & Code-Qualität
- **Lektion 01:** Typannotationen für Variablen und Funktionen (`int`, `str`, `list[str]`, `| None`)
- **Lektion 02:** Fortgeschrittene Typen (`TypeAlias`, Generics `class Box[T]:`, `NewType` / Value Objects)
- **Lektion 03:** Gute Docstrings schreiben & Linting/Formatting mit `ruff`
- **Lektion 04:** Statische Typprüfung mit `mypy` / `pyright`

### Kapitel 03: Projektmanagement & Testing
- **Lektion 01:** Virtuelle Umgebungen (`.venv`) & modernes Paketmanagement mit `uv`
- **Lektion 02:** Projektstruktur mit `pyproject.toml`, optionalen Abhängigkeiten & `__all__`
- **Lektion 03:** Automatische Unit-Tests schreiben mit `pytest`
- **Lektion 04:** Testbarkeit durch `pytest` Fixtures, Fakes und Mocks

### Kapitel 04: Moderne Software-Architektur
- **Lektion 01:** Kontextmanager (`with`-Statement & `contextlib`) für sichere Ressourcenverwaltung
- **Lektion 02:** Schnittstellen definieren mit `Protocol` (Duck Typing) & `abc.ABC`
- **Lektion 03:** Komposition statt Vererbung & Dependency Injection (DI) über `__init__`
- **Lektion 04:** Factory-Methoden (`@classmethod`) für komplexe Objekterzeugung

---

## 🟠 L3 Profi (Ziel: Eigene Claude Code Plugins entwickeln)

### Kapitel 01: Validierung, Konfiguration & Fehler-Architektur
- **Lektion 01:** JSON- und TOML-Daten verarbeiten (`json`, `tomllib` – Basis für Hook-Input/Output)
- **Lektion 02:** Datenvalidierung & Schemas mit `pydantic` (`BaseModel`)
- **Lektion 03:** Sichere Konfiguration & `.env`-Secrets mit `pydantic-settings`
- **Lektion 04:** Strukturiertes Error Handling (Eigene Exception-Hierarchien & `raise ... from err`)

### Kapitel 02: Moderne CLI-Tools, Logging & Async
- **Lektion 01:** Interaktive CLI-Anwendungen bauen mit `typer` (oder `click`) und `rich`
- **Lektion 02:** Strukturiertes Logging (`logging`, `structlog`) & Decorators als Cross-Cutting Concern
- **Lektion 03:** Einstieg in `asyncio` (`async def`, `await`, Event Loop)
- **Lektion 04:** Asynchrone API-Aufrufe & Kontextmanager mit `httpx`

### Kapitel 03: Claude Code Plugin Meisterkurs
- **Lektion 01:** Clean Plugin Architecture: Fachlogik (Domain) strikt von CLI/Dateisystem/API trennen (ohne globalen State)
- **Lektion 02:** Eigene **Claude Code Hooks** in Python programmieren (`stdin`-JSON prüfen, Exit-Codes & Entscheidungen steuern)
- **Lektion 03:** Eigenen **MCP-Server (Model Context Protocol)** in Python entwickeln und Tools bereitstellen
- **Lektion 04:** Fertiges **Claude Code Plugin** bündeln, testen und veröffentlichen (`plugin.json`, `pyproject.toml`, `uv`)
