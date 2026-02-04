```mermaid
sequenceDiagram
  participant P as Prompt
  participant M as Model

  P->>M: Large English context
  P->>M: Local language trigger
  P->>M: Arabic user text
  M-->>P: Arabic response (probabilistic)
