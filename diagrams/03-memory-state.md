```mermaid
sequenceDiagram
  participant U as User
  participant M as Model
  participant MS as Memory Summary

  U->>M: User message
  M-->>U: Response + Memory Update
  MS-->>M: Next turn state
