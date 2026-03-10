# Test: Summarizer

## Natürliche Sprache
Der Summarizer soll eine Zusammenfassung erzeugen, wenn Events vorhanden sind.

## Maschinenlesbare Struktur
input:
  events:
    - timestamp: "2024-01-01 10:00:00"
      level: "ERROR"
      message: "Something happened"

expected_contains:
  "ERROR"
