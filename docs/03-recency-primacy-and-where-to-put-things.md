# 03 — Recency, Primacy, and Where to Put Things

Most prompt engineering failures are not caused by bad wording.

They are caused by bad placement.

---

## The two forces that actually matter

LLMs exhibit two dominant biases:

Primacy bias:  
tokens near the beginning shape identity and tone.

Recency bias:  
tokens near the end dominate behavior and decisions.

Everything in the middle is weaker.

Not ignored.  
Just statistically diluted.

---

## Why "middle of the prompt" is a graveyard

People love to put important things in the middle:

- memory
- policies
- constraints
- examples

Because it feels structurally correct.

For the model, it is the worst possible place.

Middle tokens compete with:
- everything before,
- and everything after.

They have the lowest effective influence.

---

## The core mistake

Designing prompts like documents.

Humans think in:

introduction  
context  
body  
conclusion  

Models behave like:

weak influence  
weak influence  
weak influence  
strong influence  

Only the edges really matter.

---

## What actually controls output

Not:
- the most important rule,
- not the most logically correct rule,
- not the longest rule.

But:
the rule closest to generation time.

Which means:
the rule closest to the end.

---

## The real layout rule

If something must define behavior:
put it near the end.

If something must define identity:
put it near the beginning.

If something is in the middle:
assume it will partially decay.

---

## Why long system prompts drift

A long system prompt feels authoritative.

In reality:
its influence decays as context grows.

After enough tokens:
it becomes background noise.

Not gone.
Just weak.

---

## Why memory placement matters more than memory content

People ask:
"What should my memory contain?"

The more important question is:
"Where is my memory located?"

Memory in the middle:
rarely used.

Memory near the last user:
frequently used.

Same text.
Different position.
Different behavior.

---

## The recency override effect

If you have:

User: rules  
User: task  

The model interprets this as:

"new task overrides old rules"

Even if both messages are from the same user.

Order beats intent.

---

## Why this breaks intuition

Humans expect:

important things remain important.

Models behave like:

recent things become important.

Older things slowly lose power.

This is not a bug.
It is a consequence of attention mechanisms.

---

## Practical consequence

There is exactly one stable structure
if you care about control:

System:
- identity
- global constraints

User (last):
- current state
- dynamic context
- actual task

Everything else is optional noise.

---

## Mental model to keep

Do not ask:

"Is this instruction correct?"

Ask:

"Is this instruction close enough to generation
to still matter?"

Position is not cosmetic.

Position is control.
