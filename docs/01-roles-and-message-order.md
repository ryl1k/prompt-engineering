# 01 — Roles and Message Order

Most prompt engineering discussions start with roles:
System, User, Assistant.

Almost all of them are wrong about what those roles actually mean.

---

## The uncomfortable truth

For the model, roles are not layers.  
They are not isolation boundaries.  
They are not execution contexts.

They are just tokens with a training bias.

Everything the model sees is one long sequence of tokens.

The only difference is that some tokens statistically receive more attention than others.

---

## What "System" really is

System is not:
- a sandbox
- a root authority
- a protected environment

System is:
a prefix with higher prior probability weight.

In other words:
- the model is more likely to follow it,
- but it is never forced to.

There is no enforcement mechanism.  
Only probability.

---

## Why system prompts fail in practice

Because people treat system as:

"global rules that always apply"

But the model treats system as:

"the beginning of a document"

And documents can drift.

---

## The only role that actually matters

The last user message.

Not:
- the first user message,
- not the most important user message,
- not the longest user message.

The last one.

Because generation is conditioned on:

P(next_token | recent_tokens)

Not on:

P(next_token | conceptual intent)

---

## The real role hierarchy (in practice)

Not:

System > Developer > User > Assistant

But:

Last User > Everything else

System shapes behavior.  
The last user decides behavior.

---

## The biggest mistake in prompt engineering

Multiple user messages.

Example:

User: rules  
User: task

This looks logical to humans.

To the model it means:

"new task overrides old task"

You just invalidated your own rules.

---

## The only stable structure

If you care about control, there is exactly one reliable layout:

System:
- stable rules

History:
- optional and small

User (last and only decision point):
- state
- context
- task

Anything else introduces:
- recency conflicts
- instruction overrides
- format drift

---

## Why "middle of the prompt" is a graveyard

The model exhibits:
- primacy bias (beginning shapes tone)
- recency bias (end controls output)

The middle has the weakest influence.

This means:
- long system prompts decay
- memory in the middle decays
- policy blocks in the middle decay

They are not ignored.  
They are diluted.

---

## Why this breaks intuition

Humans think in structure:
- introduction
- context
- body
- conclusion

Models think in probability gradients:
- strongest influence at the edges
- weakest influence in the center

Prompt engineering fails when you design for human reading order.

---

## Practical consequence

If something must affect behavior:
- put it near the end

If something must define identity:
- put it near the beginning

Everything else is optional noise.

---

## Mental model to keep

Do not think in:
"who said what"

Think in:
"which tokens dominate the next-token distribution"

Roles are not architecture.  
They are statistical hints.

And the strongest hint is always:

The last user message.
