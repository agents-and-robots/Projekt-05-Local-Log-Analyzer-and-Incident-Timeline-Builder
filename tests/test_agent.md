# Test: Agent

## Natürliche Sprache
Der Agent soll eine Timeline und eine Summary zurückgeben (Baseline: leer).

## Maschinenlesbare Struktur
input:
  lines:
    - "[2024-01-01 10:00:00] ERROR Something happened"

expected:
  timeline: []
  summary: ""
