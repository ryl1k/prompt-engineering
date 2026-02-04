# 12 — Debugging Without Logs

Prompt engineering is debugging
without introspection.

You have:
input
output

Nothing else.

---

## The core limitation

You cannot see:
- internal reasoning
- rule application
- constraint ranking
- attention weights

You only see:
what came out.

---

## The wrong instinct

When output is wrong,
people add more instructions.

This is equivalent to:
adding code without reading errors.

It usually makes things worse.

---

## The only real debugging method

Prompt minimization.

Remove everything that is not essential
until the behavior stabilizes.

Then add things back one by one.

---

## Isolation strategy

To debug:

1. Remove memory.
2. Remove formatting.
3. Remove multilingual.
4. Remove style rules.
5. Keep only task.

If the task fails:
the model cannot do it.

If it works:
your constraints broke it.

---

## Binary testing mindset

Do not ask:
"Why is it wrong?"

Ask:
"Which constraint caused it to fail?"

Remove one thing at a time.

Observe.

---

## The most useful question

Not:
"How do I fix this output?"

But:
"What assumption did this prompt rely on
that is no longer true?"

---

## The uncomfortable truth

Most prompt bugs are not bugs.

They are overload.

The system is doing too much at once.

---

## Mental model to keep

You are not debugging logic.

You are debugging probability.
