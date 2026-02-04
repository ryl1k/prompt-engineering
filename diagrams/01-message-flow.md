```mermaid
sequenceDiagram
  participant S as System
  participant H as History
  participant U as User (current)
  participant M as Model

  S->>M: Stable rules / policy
  H->>M: Optional recent turns
  U->>M: State + Context + Task
  M-->>U: Response
