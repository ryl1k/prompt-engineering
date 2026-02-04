# 00 — Philosophy

This guide is not about making models smarter.

It is about understanding
why they behave the way they do.

---

## The core shift

Most people approach prompt engineering as:

"How do I tell the model what to do?"

This guide treats it as:

"How does this system actually work,
and how do I adapt to that reality?"

---

## What this guide assumes

You already know:
- what system / user / assistant roles are
- how to write prompts
- what RAG, memory, schemas mean
- how to call models

This guide does not teach basics.

It documents:
the invisible mechanics that shape behavior.

---

## The central mistake

People treat LLMs like:

agents that follow rules

This guide treats them like:

stochastic text generators
with attention biases and capacity limits

Everything follows from this.

---

## The real problem space

Most failures are not caused by:
- bad wording
- missing instructions
- unclear phrasing

They are caused by:
- message order
- recency bias
- instruction overload
- constraint conflicts
- format pressure
- model mismatch
- human cognitive traps

None of these are obvious from tutorials.

---

## Why this is not a "best practices" guide

Best practices imply:
there is a correct way.

There is no correct way.

There are only:
tradeoffs
failure modes
and probability shifts

This guide documents those tradeoffs.

---

## Prompt engineering as a discipline

Prompt engineering is not:
a craft
a writing skill
or a trick

It is:
systems engineering
under uncertainty

You are not programming.
You are shaping distributions.

---

## What control really means

Control does not mean:
guarantees

It means:
biasing outcomes
under constraints

Every technique in this guide:
only increases likelihood

Nothing enforces behavior.

---

## Why most advice is misleading

Most advice assumes:
models are deterministic
and instructions are executed

Both assumptions are false.

This is why:
perfect-looking prompts still fail
and simple prompts sometimes work better

---

## The guiding principle

Do not optimize for:

how your prompt looks

Optimize for:

how the model statistically reacts

---

## The uncomfortable conclusion

Prompt engineering is not about:

making models do what you want

It is about:

understanding what they can never reliably do,
and designing around that.

---

## Mental model to keep

You are not talking to a mind.

You are steering a probability field.

Everything else in this guide
is just a consequence of that fact.
