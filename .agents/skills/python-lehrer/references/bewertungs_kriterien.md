# Bewertungskriterien für den Modus `Loesung`

Prüfe die Lösung des Schülers immer passend zur aktuellen Kursstufe (keine Profi-Anforderungen aus L3 bereits in L1 verlangen!):

## 🟢 L1 Grundlagen – Checkliste
- [ ] Läuft das Skript ohne Syntax- oder Laufzeitfehler (`python3 <datei>.py`)?
- [ ] Sind alle fachlichen Anforderungen der Aufgabe erfüllt?
- [ ] Wurden sprechende Variablen- und Funktionsnamen in `snake_case` gewählt (Klassennamen in `PascalCase`, Konstanten in `UPPER_SNAKE_CASE`)?
- [ ] Werden die in der Lektion geforderten Sprachmittel (z. B. `f-Strings`, `match/case`, `@dataclass`, `try/except`) korrekt eingesetzt?
- [ ] Wurden ab Lektion `09_unveraenderlichkeit` veränderliche Standardargumente (wie `def fn(items=[]):`) vermieden?

## 🟡 L2 Fortgeschritten – Checkliste (zusätzlich zu L1)
- [ ] Sind saubere Typannotationen vorhanden (`mypy` / `pyright` fehlerfrei)?
- [ ] Ist der Code gemäß `ruff` sauber formatiert und frei von Linting-Warnungen?
- [ ] Sind kurze, klare Docstrings für Module, Klassen und Funktionen vorhanden?
- [ ] Werden Ressourcen sicher über Kontextmanager (`with`) verwaltet?
- [ ] Sind Funktionen/Klassen entkoppelt (Komposition, `Protocol`, Dependency Injection) und über `pytest` testbar?

## 🟠 L3 Profi (Plugin-Entwicklung) – Checkliste (zusätzlich zu L1 & L2)
- [ ] Werden externe Eingaben (JSON von `stdin`, CLI-Argumente, `.env`, TOML) sauber mit `pydantic` validiert?
- [ ] Werden eigene Exceptions sinnvoll eingesetzt und mit `raise ... from err` verkettet?
- [ ] Ist die Fachlogik (Domain) strikt von Infrastruktur (CLI, Dateisystem, HTTP/MCP) getrennt?
- [ ] Gibt es keinen versteckten globalen veränderbaren Zustand?
- [ ] Werden für Claude Code Hooks / MCP-Server `stdout` (nur für strukturiertes Protokoll/JSON) und `stderr` / Logging sauber getrennt?
