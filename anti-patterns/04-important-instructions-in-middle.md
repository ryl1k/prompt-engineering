## 4. Important Instruction in the Middle

### What it is

Placing critical rules in the middle of a long prompt.

### Why people do it

Because it matches how humans write documents:

* introduction
* context
* main content
* conclusion

Important things go in the "body".

### What actually happens

Middle tokens have the weakest influence.

They compete with everything before and after.

### Typical symptoms

* key rules appear to be ignored
* behavior follows recent text instead
* inconsistent enforcement

### Why intuition fails

Humans expect importance to persist.
Models apply recency dominance.

Position beats meaning.

```mermaid
flowchart TD
  A[Important rule in middle] --> B[Weak attention]
  B --> C[Overridden by end]
