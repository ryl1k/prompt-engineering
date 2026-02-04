## 8. Rewrite System from User

### What it is

Asking user-layer instructions to override system rules.

### Why people do it

Because it feels flexible and powerful.

### What actually happens

System and user constraints compete.

Outcome becomes unstable.

### Typical symptoms

* sometimes ignores system
* sometimes ignores user
* unpredictable compliance

### Why intuition fails

There is no true override mechanism.

Only dominance competition.

```mermaid
flowchart TD
  A[User: ignore above] --> B[Conflict]
  B --> C[Unstable behavior]