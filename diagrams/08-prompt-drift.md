```mermaid
stateDiagram-v2
  [*] --> Working
  Working --> SlightDrift
  SlightDrift --> Broken
  Broken --> Rewrite
  Rewrite --> Working
