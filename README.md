# Local Log Analyzer & Incident Timeline Builder (Offline, CPU-only)

Dieses Projekt analysiert lokale Logfiles und erzeugt daraus eine Incident-Timeline.
Es arbeitet vollständig offline, benötigt keine GPU und verwendet keine KI-Modelle.

Funktionen:
- Logzeilen parsen
- Events extrahieren
- Schweregrad heuristisch bestimmen
- Timeline sortieren
- kurze Incident-Zusammenfassung erzeugen

Das Projekt demonstriert:
- deterministische Log-Analyse
- heuristische Bewertung
- Timeline-Erzeugung
- Prompt-Driven Development (PDD)

## Projektstruktur

/src  
    parser.py  
    classifier.py  
    timeline_builder.py  
    summarizer.py  
    agent.py  

/docs  
    architecture.md  

/tests  
    test_parser.md  
    test_classifier.md  
    test_timeline_builder.md  
    test_summarizer.md  
    test_agent.md  

hardware-requirements.md  
instructions.md  
README.md  
credits.md

## Hardware Requirements

Dieses Projekt ist vollständig lokal ausführbar und benötigt keine spezielle Hardware.
Siehe `hardware-requirements.md`.

## Lizenz

MIT License.

## Credits

Siehe `credits.md`.
