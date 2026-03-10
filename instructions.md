# LLM Instructions – Local Log Analyzer & Incident Timeline Builder (Offline)

Diese Datei definiert alles, was ein LLM benötigt, um dieses Projekt vollständig selbständig umzusetzen:
- Input/Output-Protokoll
- Modul- und Agenten-Logik
- Regelwerk
- Hardware-Constraints
- How-To-Use

---

## 1. Ziel

Erstelle ein System, das Logzeilen analysiert, Events extrahiert, Schweregrade zuweist,
eine chronologische Incident-Timeline baut und eine kurze Zusammenfassung erzeugt — vollständig offline.

---

## 2. Hardware Constraints

Dieses Projekt muss vollständig auf normaler Consumer-Hardware lauffähig sein:

- CPU-only
- keine GPU-Abhängigkeiten
- keine Modelle > 1 GB
- keine externen APIs oder Cloud-Dienste
- alles offline
- Python-Standardbibliothek

---

## 3. Modul-Spezifikationen

### 3.1 Parser (/src/parser.py)

Signatur: parse(lines: list[str]) -> list[dict]

Aufgabe:
- Logzeilen in strukturierte Events umwandeln

Rückgabeformat (Events):
- timestamp: string
- level: string (z. B. INFO, WARN, ERROR)
- message: string

---

### 3.2 Classifier (/src/classifier.py)

Signatur: classify(events: list[dict]) -> list[dict]

Aufgabe:
- Schweregrad heuristisch bestimmen

Rückgabeformat:
- events mit zusätzlichem Feld:
  - severity: string (low, medium, high, critical)

---

### 3.3 Timeline Builder (/src/timeline_builder.py)

Signatur: build(events: list[dict]) -> list[dict]

Aufgabe:
- Events nach timestamp sortieren
- optional filtern (z. B. nur severity >= medium)

---

### 3.4 Summarizer (/src/summarizer.py)

Signatur: summarize(events: list[dict]) -> str

Aufgabe:
- kurze, deterministische Incident-Zusammenfassung erzeugen
- keine KI, nur heuristische Regeln

---

### 3.5 Agent (/src/agent.py)

Signatur: run(lines: list[str]) -> dict

Aufgabe:
- orchestriert parser, classifier, timeline_builder, summarizer

Rückgabeformat:
- timeline: list[dict]
- summary: string
- steps: list[str]

---

## 4. Orchestrator-Logik

1. events = parse(lines)
2. classified = classify(events)
3. timeline = build(classified)
4. summary = summarize(timeline)
5. Ergebnis zurückgeben

---

## 5. Regelwerk / Constraints

### Parser
- deterministisch
- einfache Patterns (z. B. "[2024-01-01 10:00:00] ERROR Something happened")

### Classifier
- heuristisch:
  - ERROR → high
  - WARN → medium
  - INFO → low

### Timeline
- sortiert nach timestamp (string oder parsed)

### Summary
- deterministisch
- z. B.:
  - Anzahl Events pro Severity
  - erster und letzter Timestamp
  - wichtigste ERROR-Meldung

---

## 6. Aufgaben an das LLM

Das LLM soll:

1. parser.py implementieren  
2. classifier.py implementieren  
3. timeline_builder.py implementieren  
4. summarizer.py implementieren  
5. agent.py implementieren  
6. architecture.md ergänzen  
7. Tests in /tests aktualisieren  

---

## 7. How-To-Use (für Code-Assistenten)

1. Öffne das Repository.  
2. Öffne `instructions.md`.  
3. Markiere den gesamten Inhalt.  
4. Sende ihn an deinen Code-Assistenten mit:

„Lies diese instructions.md vollständig. Implementiere dann alle beschriebenen Module und Dateien. Halte dich strikt an das Input/Output-Protokoll, das Regelwerk und die Hardware-Constraints. Beginne mit parser.py.“

Damit kann ein LLM das Projekt vollständig autonom umsetzen.
