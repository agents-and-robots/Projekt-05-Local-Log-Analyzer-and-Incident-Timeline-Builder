# Test: Parser

## Natürliche Sprache
Der Parser soll aus einer Logzeile ein Event mit timestamp, level und message erzeugen.

## Maschinenlesbare Struktur
input:
  lines:
    - "[2024-01-01 10:00:00] ERROR Something happened"

expected:
  events_count: 1
  first_event_level: "ERROR"
