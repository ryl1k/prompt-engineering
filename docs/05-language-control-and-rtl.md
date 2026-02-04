# 05 — Language Control and RTL

Language control in LLMs is not a feature.

It is a side effect.

And it is never guaranteed.

---

## The core illusion

People think models do this:

"I detect the user's language and respond in it."

Models actually do this:

"I continue the most likely linguistic pattern
present in the recent tokens."

There is no language selector.
There is no internal switch.
Only probability.

---

## Why "always respond in user's language" fails

Because "always" is just another token.

It does not introduce enforcement.
It only slightly shifts probabilities.

In long contexts:
- it decays,
- it gets overridden,
- or it is ignored.

Especially when:
- system is in English,
- memory is in English,
- examples are in English,
- formatting rules are in English.

The model drifts to English because:
it is statistically easier.

---

## The real control mechanism

Language is controlled by:
the last dominant linguistic signal.

Not by:
- the longest block,
- the most important block,
- or the most logical block.

But by:
the most recent block
that clearly activates a language mode.

---

## Why short language hints are weak

Five tokens in Arabic
after 2000 tokens in English
is not a strong signal.

It can be interpreted as:
- a quote,
- an example,
- or noise.

The model may continue in English
because English is still dominant in context.

---

## The local trigger pattern

The strongest prompt-only technique
is a local instruction placed
directly before the user text.

Example:

Respond in the language used below:

<user message>

This works better than:
any global system rule.

Because it creates:
a direct association between
instruction and data.

---

## Why this is still not reliable

Even the local trigger:
- can be overridden,
- can be ignored,
- can conflict with formatting rules.

Especially when:
- output grammar is strict,
- Markdown constraints exist,
- or the model prefers English for structure.

This is not a bug.
It is a consequence of probability blending.

---

## RTL-specific failure modes

Arabic introduces additional instability:

- mixed RTL and LTR in one line,
- Latin technical terms breaking flow,
- punctuation order inversion,
- Markdown symbols disrupting direction.

The model often chooses English
simply because:
it is easier to format.

---

## Practical RTL rules (prompt-only)

These do not guarantee correctness,
but reduce failure rates:

- Avoid mixing Arabic and English
  in the same line when possible.
- Isolate Latin terms in parentheses.
- Keep Arabic user message "clean":
  no English labels like USER_MESSAGE.
- Avoid complex Markdown structures
  when responding in Arabic.

---

## The hard limit

Without validation or retries:

There is no way to guarantee
correct language selection.

All techniques only:
shift probabilities.

---

## The honest engineering mindset

Stop asking:

"How do I force the model
to respond in this language?"

Start asking:

"How do I make this language
the easiest continuation path
given all competing constraints?"

---

## Mental model to keep

Language is not a parameter.

It is a statistical attractor.

And attractors can always lose.
