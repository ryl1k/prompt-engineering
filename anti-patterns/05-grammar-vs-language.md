## 5. Grammar vs Language

### What it is

Combining strict output grammar with multilingual requirements.

### Why people do it

Because they want:

* machine-readable output
* and correct user language

At the same time.

### What actually happens

The model prioritizes not breaking structure.

Language becomes secondary.

### Typical symptoms

* answers in English despite non-English input
* mixed languages
* shallow content to stay valid

### Why intuition fails

Grammar is easier to verify than semantics.

The model chooses the safest path.

```mermaid
flowchart LR
  A[Strict grammar] --> C[Dominant output]
  B[Language rule] --> C
  C --> D[Grammar wins, language lost]
