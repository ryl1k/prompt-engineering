## 9. Patch with More Rules

### What it is

Treating prompt failures like software bugs.

### Why people do it

Because programming habits carry over.

### What actually happens

Each new rule introduces new conflicts.

Entropy increases.

### Typical symptoms

* constant prompt rewrites
* regressions
* no stable behavior

### Why intuition fails

More constraints reduce dominance.

Control comes from subtraction, not addition.

```mermaid
flowchart TD
  A[Bug appears] --> B[Add rule]
  B --> C[New conflict]
  C --> D[System collapse]