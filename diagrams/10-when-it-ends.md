```mermaid
flowchart TD
  A[Prompt-only system] --> B[Increasing constraints]
  B --> C{Need guarantees?}
  C -->|No| D[Keep prompt]
  C -->|Yes| E[Add control layer]
