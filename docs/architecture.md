# Architektur – Local Log Analyzer & Incident Timeline Builder

## Module

- parser.py – parst Logzeilen in Events
- classifier.py – bewertet Schweregrad
- timeline_builder.py – baut Timeline
- summarizer.py – erzeugt Zusammenfassung
- agent.py – orchestriert den Prozess

## Datenfluss

1. Parser erzeugt Events
2. Classifier bewertet Events
3. Timeline Builder sortiert Events
4. Summarizer erzeugt Incident-Zusammenfassung
5. Agent orchestriert alles
