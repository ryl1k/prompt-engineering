## 1. Multiple User Messages

### What it is

Splitting rules and tasks into multiple User messages.

Example:

User: rules
User: task

### Why people do it

Because it matches human logic:

* first define behavior
* then give the actual request

This feels clean and structured.

### What actually happens

The model treats the last user message as the real instruction.

Earlier user messages are not global rules.
They are just older text.

### Typical symptoms

* ignores earlier constraints
* format and language drift
* rules apply only sometimes

### Why intuition fails

Humans think in logical hierarchy.
Models operate on recency dominance.

The last user message wins.

```mermaid
flowchart TD
  A[User: Rules] --> B[User: Task]
  B --> C[Model]
  C --> D[Task overrides rules]
