## 3. Too Many Rules

### What it is

Continuously adding new rules to fix failures.

### Why people do it

Because it feels like programming:

* bug appears
* add constraint
* expect fix

### What actually happens

Instruction capacity is exceeded.

Rules stop stacking and start averaging.

### Typical symptoms

* random rule drops
* unstable format
* partial compliance

### Why intuition fails

Models do not perform logical AND.
They perform probabilistic blending.

More rules reduces dominance.

```mermaid
flowchart TD
  A[Add rules] --> B[Instruction load]
  B --> C[Capacity exceeded]
  C --> D[Soft averaging]
  D --> E[Unstable behavior]
