# Prompt Engineering Anti-Patterns

This section documents systematic failure modes in prompt engineering.

Not mistakes.  
Not edge cases.  

But patterns that:
- look reasonable,
- feel logical,
- and consistently break systems.

These are not “things to avoid”.  
These are things people naturally do, and only later realize why everything drifted.

---

## What this is

These are anti-patterns.

Each one describes:
- a common design decision,
- why it feels correct,
- what actually happens in practice,
- and why human intuition fails.

They are written as engineering diagnostics, not advice.

---

## Why anti-patterns matter

Most prompt systems do not fail because of:

- bad wording,
- unclear instructions,
- or lack of examples.

They fail because of structural mistakes:

- wrong message order,
- wrong memory model,
- too many constraints,
- misplaced rules,
- format overuse.

Anti-patterns make these failures visible.

---

## Index

1. [Multiple User Messages](./01-multiple-users.md)  
2. [Memory as Chat Log](./02-memory-as-log.md)  
3. [Too Many Rules](./03-too-many-rules.md)  
4. [Important Instruction in the Middle](./04-important-in-middle.md)  
5. [Grammar vs Language](./05-grammar-vs-language.md)  
6. [Format Everything](./06-format-everything.md)  
7. [Examples in the Middle](./07-examples-in-middle.md)  
8. [Rewrite System from User](./08-rewrite-system.md)  
9. [Patch with More Rules](./09-patch-with-more-rules.md)

---

## How to use this section

You don’t read this as a tutorial.

You use it when:

- a system becomes unstable,
- behavior starts drifting,
- memory stops working,
- language changes unexpectedly,
- adding rules makes things worse.

Find the anti-pattern that matches your situation.

The fix is usually:
simplification, not optimization.

---

## Mental model

If something feels:
- logical  
- well structured  
- similar to software design  

It is probably dangerous in prompt engineering.

Models do not fail loudly.  
They decay silently.

Anti-patterns exist to show where that decay comes from.
