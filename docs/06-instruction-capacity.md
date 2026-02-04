# 06 — Instruction Capacity (Cognitive Budget)

Every model has a real, hard limit
on how many instructions it can hold at once.

Not context length.

Instruction capacity.

---

## The invisible limit

People think:

"If the model can see it, it can use it."

This is false.

Models have a limited capacity
to maintain independent constraints.

After that limit:
instructions stop stacking
and start averaging.

---

## What actually breaks

When instruction capacity is exceeded:

- some rules are ignored
- some are weakened
- some randomly dominate
- behavior becomes unstable

The model does not fail loudly.

It degrades silently.

---

## Typical capacity ranges (practical)

Very approximate, but realistic:

Small models (7B–13B):
- 3 to 5 independent rules

Mid models:
- 5 to 8 independent rules

Large models (GPT-4 class):
- 8 to 12 independent rules

After that:
you are not adding control,
you are adding noise.

---

## What counts as an "instruction"

An instruction is any constraint that requires:
- remembering a rule
- applying it conditionally
- or shaping output structure

Examples of separate instructions:

- respond in user's language
- output valid Markdown
- include image tokens
- follow safety policy
- keep friendly tone
- avoid certain topics
- respect formatting rules

Each one consumes budget.

---

## Why more rules often reduce compliance

Because the model does not perform logical AND.

It performs probabilistic blending.

With too many rules:
no single rule remains dominant.

Everything becomes "kind of applied".

---

## The false safety instinct

When behavior is wrong,
people instinctively add more rules.

"Be more strict."
"Never do X."
"Always do Y."

This almost always makes things worse.

You are increasing load,
not increasing control.

---

## The compression principle

One strong instruction
beats five weak ones.

Example:

Bad:
- always respond in user's language
- never mix languages
- detect language first
- choose correct locale
- use same alphabet

Better:
- respond in the same language as the last user message

Same intent.
One instruction.
Lower cognitive cost.

---

## Instruction collapse pattern

Common failure pattern:

1. System prompt grows.
2. Behavior improves temporarily.
3. More edge cases appear.
4. More rules are added.
5. Behavior becomes inconsistent.
6. People blame the model.

The real cause:
instruction overload.

---

## How to design within capacity

Practical rules:

- Merge related rules into one.
- Prefer concrete rules over abstract ones.
- Remove rules that are rarely tested.
- Eliminate stylistic rules first.
- Keep format rules minimal.

---

## The harsh truth

There is no way to bypass
instruction capacity with wording.

You cannot "explain better".

You can only:
- simplify
- compress
- or remove.

---

## Mental model to keep

Treat instructions like RAM.

Once you exceed capacity:
the system still runs,
but behavior becomes undefined.

More instructions
is not more intelligence.

It is more entropy.
