## 2. Memory as Chat Log

### What it is

Using raw conversation history as memory.

Appending full dialogue instead of summarizing state.

### Why people do it

Because:

* it is already available
* it feels like real memory
* it requires no extra design

### What actually happens

The model does not reason over history.
It just sees more tokens.

Important facts become statistically weaker over time.

### Typical symptoms

* forgets user preferences
* repeats the same questions
* inconsistent behavior across turns

### Why intuition fails

Humans think memory is stored experiences.
Models treat memory as recent token conditioning.

History is not memory.
It is noise with a timestamp.

```mermaid
flowchart TD
  A[Chat history grows] --> B[Context length increases]
  B --> C[Signal per token drops]
  C --> D[Memory ignored]
