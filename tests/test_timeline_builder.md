# Test: Timeline Builder

## Natürliche Sprache
Der Timeline Builder soll Events nach timestamp sortieren.

## Maschinenlesbare Struktur
input:
  events:
    - timestamp: "2024-01-01 11:00:00"
      level: "INFO"
      message: "Later"
    - timestamp: "2024-01-01 10:00:00"
      level: "ERROR"
      message: "Earlier"

expected:
  first_event_timestamp: "2024-01-01 10:00:00"
