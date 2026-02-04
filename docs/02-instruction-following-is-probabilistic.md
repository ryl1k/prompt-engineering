# 02 — Instruction Following Is Probabilistic

Most people talk about instruction following as if it were a feature.

It is not.

It is an emergent statistical behavior.

---

## The core misconception

People think models do this:

"I received an instruction. I will execute it."

Models actually do this:

"I will generate the most likely continuation of text
given everything I have seen so far."

There is no execution layer.  
There is no rule engine.  
There is no internal validator.

Only probability.

---

## Why instructions feel real

Instructions appear to work because:

- training data contains many instruction-like texts,
- models learned patterns where instructions are followed,
- so they reproduce those patterns.

Not because they understand obligation.

Not because they understand rules.

Not because they check compliance.

---

## What the model actually optimizes

The model does not optimize:

correctness  
consistency  
safety  
or policy adherence

It optimizes:

likelihood of next token.

Everything else is an illusion created by training distribution.

---

## Why "perfect prompts" still fail

Because you are not controlling logic.

You are shaping probabilities.

Even a perfect prompt only means:

"the desired behavior is now more likely than before"

Not:

"the behavior is guaranteed"

---

## The hidden failure mode

When multiple constraints exist:

- format rules
- language rules
- safety rules
- task rules
- style rules

The model does not perform a logical AND.

It performs a soft blend.

Some constraints will be weakened.
Some will be ignored.
Some will dominate.

Which ones dominate changes between generations.

---

## Why "Always" and "Never" are meaningless

Tokens like:

always  
never  
must  
strictly  
guaranteed  

Do not introduce enforcement.

They only slightly shift probability mass.

They feel strong to humans.
They are weak to models.

---

## Why instruction conflicts are unavoidable

If your prompt contains:

- more than 5 to 7 independent rules,
- or rules at different abstraction levels,
- or rules that compete for output structure,

You have already created an unstable system.

The model will pick a subset.
Which subset changes over time.

---

## The illusion of control

Prompt engineering feels like programming because:

- the surface form looks like code,
- the model often behaves consistently,
- small changes can cause large effects.

But underneath, there is no program.

There is only sampling from a distribution.

---

## Practical consequences

You cannot force behavior.
You can only increase or decrease its likelihood.

There is no such thing as:
- "fully compliant"
- "guaranteed following"
- "deterministic instruction execution"

There is only:
- higher probability
- lower probability

---

## The engineering mindset

Stop asking:

"How do I make the model follow this rule?"

Start asking:

"How do I make this behavior statistically dominant
over all competing behaviors?"

---

## Mental model to keep

LLMs are not agents that obey instructions.

They are stochastic generators that imitate
documents where instructions were obeyed.

Prompt engineering is not rule design.

It is probability shaping under uncertainty.
