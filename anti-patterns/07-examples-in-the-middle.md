## 7. Examples in the Middle

### What it is

Placing few-shot examples far from the actual task.

### Why people do it

Because examples feel like background context.

### What actually happens

Example influence decays.

The model follows recent tokens instead.

### Typical symptoms

* ignores example style
* wrong structure
* inconsistent patterns

### Why intuition fails

Examples only work when they are recent.

Position activates patterns.

```mermaid
flowchart TD
  A[Examples added] --> B[Placed in middle]
  B --> C[Weak activation]