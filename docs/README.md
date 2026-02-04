# Prompt Engineering Field Guide — Docs

This folder contains the core of the guide.

Each file documents a real failure mode or hidden constraint
that most people only discover after shipping systems.

These are not tutorials.
They are engineering notes.

---

## Reading order (recommended)

If you want the full mental model, read in this order:

### Foundations
- [00 — Philosophy](./00-philosophy.md)  
- [01 — Roles and Message Order](./01-roles-and-message-order.md)  
- [02 — Instruction Following Is Probabilistic](./02-instruction-following-is-probabilistic.md)  
- [03 — Recency, Primacy, and Where to Put Things](./03-recency-primacy-and-where-to-put-things.md)  

### Memory and Language
- [04 — Memory Without a Backend](./04-memory-without-backend.md)  
- [05 — Language Control and RTL](./05-language-control-and-rtl.md)  

### System Limits
- [06 — Instruction Capacity](./06-instruction-capacity.md)  
- [07 — Constraint Dominance](./07-constraint-dominance.md)  
- [08 — Output Grammar](./08-output-grammar.md)  
- [09 — Format Pressure and Semantic Collapse](./09-format-pressure.md)  
- [10 — Model Calibration](./10-model-calibration.md)  

### Engineering Reality
- [11 — Prompt Drift Over Time](./11-prompt-drift.md)  
- [12 — Debugging Without Logs](./12-debugging-without-logs.md)  
- [13 — Human Illusion Traps](./13-human-illusion-traps.md)  
- [14 — When Prompt Engineering Ends](./14-when-prompt-engineering-ends.md)  

---

## How to use these docs

These files are meant to be:

- read slowly
- questioned
- tested against real prompts

Not memorized.
Not treated as rules.

If something feels "wrong" or "too cynical",
it probably reflects a real production failure mode.

---

## What these docs are not

This is not:

- a list of prompt patterns
- a collection of tricks
- a beginner course
- a model-specific manual

There are no magic phrases here.

Everything described is:
- model-agnostic
- prompt-only
- and fundamentally probabilistic

---

## The underlying assumption

All techniques here assume:

- no external validators
- no retries
- no backend control
- no tool calling
- no function schemas

Just:
one prompt → one response

---

## How to extend this guide

If you add new chapters, they should:

- describe a real failure mode
- explain why intuition breaks
- show the statistical cause
- avoid giving "recipes"
- focus on limits, not hacks

This guide is about:
understanding the system,
not pretending it is something else.

---

## Mental model

Do not treat this as documentation.

Treat it as:
a map of invisible constraints
that shape every LLM interaction.
