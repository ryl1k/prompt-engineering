# 08 — Output Grammar

The moment you introduce things like:

- strict JSON
- fixed templates
- special tokens
- image markers
- custom delimiters

You are no longer working with natural language.

You are inventing a new language.

---

## The core problem

LLMs are trained on:
natural human text.

They are not trained on:
your invented output grammar.

So every time you require:
```
[[image=1]]  
<END>  
|||  
{ "key": "value" }
```
You are forcing the model to:
speak a language that barely exists in its training data.

---

## Why this creates instability

You are asking the model to:

1. think semantically  
2. generate content  
3. obey a formal grammar  

At the same time.

These tasks compete.

When pressure increases:
grammar wins,
semantics loses.

---

## The grammar collision effect

Natural language wants to be:
flexible, expressive, redundant.

Formal grammar wants to be:
rigid, minimal, deterministic.

The model cannot fully satisfy both.

So it compromises:
- simpler ideas
- generic phrasing
- dropped nuance
- reduced creativity

This is not a bug.
It is a structural conflict.

---

## Why every extra symbol is expensive

Each new marker:

```
[[image=1]]  
<quote>  
::section::  
@@@
```

is a new rule.

Each rule consumes instruction capacity.

Ten markers are not ten characters.

They are ten competing constraints.

---

## The false sense of safety

People think:

"With grammar, I get control."

In reality:
you trade semantic quality
for structural predictability.

You did not gain control.
You shifted failure modes.

---

## Why grammar often dominates everything else

Because grammar is:
- easy to verify
- easy to break
- highly represented in training

So the model prioritizes:
"not breaking grammar"

Over:
- correctness
- language fidelity
- context usage
- memory consistency

---

## The minimal grammar principle

The best output grammar is:

the smallest one that still works.

Every additional token should justify itself.

If you need:
- three delimiters
- multiple nesting rules
- or several marker types

Your grammar is already too complex.

---

## Common grammar mistakes

- Mixing grammar with prose.
- Embedding markers inside lists or tables.
- Allowing free text before or after structured blocks.
- Using multiple competing grammars at once.

Each one increases entropy.

---

## Practical rules

If you must use output grammar:

- Keep it flat.
- Keep it minimal.
- Keep it visually distinct.
- Never nest grammar inside grammar.
- Never mix multiple grammars.

---

## The hard tradeoff

You cannot have:

- perfect semantics  
and  
- perfect grammar  

in the same output.

You always choose which one matters more.

---

## Mental model to keep

Output grammar is not control.

It is a tax.

You pay with:
- expressiveness
- reliability
- and model capacity.

Use it only when you must.
