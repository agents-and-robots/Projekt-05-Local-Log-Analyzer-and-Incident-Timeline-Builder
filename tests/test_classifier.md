# Test: Classifier

## Natürliche Sprache
Der Classifier soll ERROR-Events als high einstufen.

## Maschinenlesbare Struktur
input:
  events:
    - timestamp: "2024-01-01 10:00:00"
      level: "ERROR"
      message: "Something happened"

expected:
  first_event_severity: "high"
