# 🐍 Interaktiver Python-Kurs: Von Null zum eigenen Claude Code Plugin

Willkommen zu deinem persönlichen, KI-gestützten Python-Programmierkurs!
In diesem Projekt ist die **KI dein Programmierlehrer** und **du bist der Schüler**. Du lernst Python Schritt für Schritt von den allerersten Grundlagen (`L1`) über fortgeschrittene Techniken (`L2`) bis zur Entwicklung eigener **Claude Code Plugins, Hooks, CLI-Tools und MCP-Server** (`L3`).

---

## 🚀 1. Wie funktioniert das Projekt im Alltag?

Alle Lektionen liegen im Ordner [`kurs/`](./kurs/) und sind in **Stufen -> Kapitel -> Einzel-Lektionen** unterteilt. Jede Lektion behandelt **nur ein einziges Thema**, damit es für Anfänger nie zu schwer wird. Alle Ordner starten leer – du schreibst den Code selbst!

### Dein Ablauf für jede Lektion (4 einfache Befehle):

| Schritt | Befehl im Chat (Agy / Codex) | Slash-Command (Claude / Copilot) | Was passiert? |
| :--- | :--- | :--- | :--- |
| **1. Starten** | `Aufgabe_Lesen` | `/aufgabe` | Der KI-Lehrer schaut in [`FORTSCHRITT.md`](./FORTSCHRITT.md), erklärt das Thema kurz (**max. 20 % Theorie**, ohne Code-Spoiler!) und gibt dir eine kleine Aufgabe für den aktuellen Ordner. |
| **2. Üben** | `Aktives_Coden` | `/aktiv` | *(Optional)* Trainiere mit **Active Recall**: Du liest ein kurzes Beispiel, blendest es aus und baust deine Lösung aus dem Gedächtnis („From Scratch“) im Lektionsordner. |
| **3. Hilfe holen** | `Frage` | `/frage` | Wenn du nach **mindestens 5 Minuten** eigenem Probieren feststeckst, gibt dir der Lehrer einen gezielten Tipp zu genau deiner Hürde – ohne dir den fertigen Code vorwegzunehmen. |
| **4. Abgeben** | `Loesung` | `/loesung` | Der Lehrer prüft und testet deine `.py`-Datei im aktuellen Ordner, gibt dir Feedback und hakt die Lektion bei Erfolg automatisch in [`FORTSCHRITT.md`](./FORTSCHRITT.md) ab. |

---

## 🧠 2. Welches Sprachmodell (LLM) solltest du nutzen? *(Stand: Ende 2026)*

Da die Lektionen kleinschrittig aufgebaut sind und der Lehrer-Skill klare Vorgaben hat, **brauchst du keine teuren Frontier-/Heavy-Reasoning-Modelle**. Schnelle 2026er Standard- und Flash-Modelle antworten sofort und sparen dir enorm viel Token-Kontingent!

### Aktuelle Modell-Empfehlung (2026) nach KI-Tool

| KI-Tool | ⚡ Besonders sparsam & schnell (`L1 Grundlagen`) | 🏆 Beste Wahl für den Alltag (`L1–L3 Standard`) | 🔬 Für komplexe Plugin-Architektur (`L3 Profi`) | ❌ Im Kurs vermeiden *(zu teuer / frisst Quota)* |
| :--- | :--- | :--- | :--- | :--- |
| **Antigravity CLI (`agy`)** | **Gemini 3.8 Flash** oder **Gemini 4 Hydrogen** | **Gemini 4 Argon (Low / Medium)** *(aktuell aktiv!)* | **Gemini 4 Argon (High)** oder **Gemini 4 Carbon** | `xhigh`-Thinking im Anfängerteil |
| **Claude Code** | **Claude Haiku 5.5** (`claude-haiku-5-5`) | **Claude Sonnet 5.5** (`claude-sonnet-5-5`) | **Claude Sonnet 5.5** *(reicht auch für L3 völlig!)* | **Claude Opus 5.5** & **Claude Fable 5.2** |
| **OpenAI Codex CLI** | **GPT-6 Luna** (`codex -m gpt-6-luna`) oder **GPT-5.4 nano** | **GPT-6.2 Sol** (`gpt-6.1-sol` / `gpt-5.3-codex`) | **GPT-6.2 Sol** | **GPT-6.2 Astra** (Heavy Reasoning) |
| **GitHub Copilot (VS Code)** | **Gemini 3.8 Flash**, **Claude Haiku 5.5** oder **MAI Code 2 Flash** | **Claude Sonnet 5.5**, **GPT-6.2 Sol** oder **Gemini 4 Hydrogen** | **Claude Sonnet 5.5** oder **Gemini 4 Argon** | **Claude Fable 5.2** / **GPT-6.2 Astra** |

### Wann welches Modell? (Faustregel für deinen Kurs)
1. **🟢 L1 Grundlagen & 🟡 L2 Fortgeschritten (ca. 80 % des Kurses):**
   * **In Agy CLI:** Bleib bei **Gemini 4 Argon (Medium/Low)**, **Gemini 4 Hydrogen** oder **Gemini 3.8 Flash**.
   * **In Claude Code:** Wechsle mit `/model sonnet` auf **Claude Sonnet 5.5** oder mit `/model haiku` auf **Claude Haiku 5.5** (Standard in Claude Code ist oft *Opus 5.5* – der Wechsel auf Sonnet 5.5 halbiert sofort deinen Verbrauch!).
   * **In Codex CLI:** Nutze mit `/model` **GPT-6 Luna** oder **GPT-6.2 Sol**.
2. **🟠 L3 Profi (Claude Code Hooks, Async, MCP-Server):**
   Nutze **Gemini 4 Argon (Medium/High)**, **Claude Sonnet 5.5** oder **GPT-6.2 Sol**.
3. **Warum keine Flaggschiffe wie *Claude Fable 5.2*, *Opus 5.5* oder *GPT-6.2 Astra*?**
   Diese Modelle sind für stundenlanges Refactoring riesiger Codebasen gebaut. Für unsere kleinen 20-Zeilen-Lernaufgaben denken sie unnötig lange nach und verbrauchen das **4- bis 20-fache deines Token-Budgets** ohne besseren Lerneffekt.

---

## 🛠️ 3. Bedienung in deinen 4 Tools

Du kannst jederzeit zwischen den Tools wechseln, weil alle 4 denselben Stand aus [`FORTSCHRITT.md`](./FORTSCHRITT.md) lesen:

* **In Antigravity CLI (`agy`):**
  Einfach im Projektordner starten und tippen:
  `Aufgabe_Lesen` (oder `Frage`, `Loesung`, `Aktives_Coden`)
* **In Claude Code:**
  Nutze direkt die eingerichteten Slash-Commands:
  `/aufgabe`, `/frage`, `/loesung` oder `/aktiv` *(Tipp: Vorher `/model sonnet` oder `/model haiku` wählen!)*
* **In OpenAI Codex CLI:**
  Tippe einfach `Aufgabe_Lesen`, `Frage`, `Loesung` oder rufe `$python-lehrer` auf *(Tipp: Vorher `/model` -> `gpt-6-luna` oder `gpt-6.2-sol` wählen!)*.
* **In GitHub Copilot Chat (VS Code):**
  Nutze im Chat die Prompt-Befehle `/aufgabe`, `/frage`, `/loesung` oder `/aktiv`.

---

## 💡 4. Drei goldene Tipps zum Token-Sparen

1. **Ein neuer Chat pro Lektion (oder Kapitel):**
   Starte nach 1–2 abgeschlossenen Lektionen einfach einen neuen Chat (`/clear` oder neues Gespräch). Da dein Stand in [`FORTSCHRITT.md`](./FORTSCHRITT.md) gespeichert ist, weiß der neue Chat sofort Bescheid, ohne den alten Verlauf jedes Mal neu einzulesen!
2. **`/compact` nutzen:**
   Wenn du länger in einer Sitzung bleibst, nutze zwischendurch `/compact`, um den Chatverlauf zusammenzufassen.
3. **Direkt starten:**
   Deine erste Lektion wartet bereits in:
   `kurs/L1_Grundlagen/Kapitel_01_Erste_Schritte_Variablen/Lektion_01_print_hallo_welt/`
   Tippe jetzt einfach **`Aufgabe_Lesen`** (oder **`/aufgabe`**)!
