```mermaid
flowchart TD
  A[More rules] --> B[Instruction load]
  B --> C{Capacity exceeded?}
  C -->|No| D[Mostly stable]
  C -->|Yes| E[Soft averaging]
  E --> F[Unstable behavior]
