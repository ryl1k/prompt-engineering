```mermaid
flowchart TD
  A[Wrong output] --> B[Remove memory]
  B --> C[Remove format]
  C --> D[Remove multilingual]
  D --> E[Minimal prompt]
  E --> F{Still broken?}
  F -->|Yes| G[Model limit]
  F -->|No| H[Constraint overload]
