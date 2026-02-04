# Prompt Engineering Patterns

This section documents stable prompt architectures.

Not perfect.
Not guaranteed.

Just patterns that:
- degrade slower,
- drift less,
- and survive complexity longer.

Patterns are not solutions.
They are structural compromises.

---

## What patterns are

Patterns describe:
- message layout
- memory design
- rule placement
- constraint boundaries

They do not describe:
- wording tricks
- magic system prompts
- model-specific hacks

---

## 1. Single-User Pattern

### Description

Exactly one User message per turn.

All state, context, and task are merged into it.

### Why it works

Because:
- recency dominance is preserved
- no user-layer conflicts exist
- the model has one clear decision point

### Trade-offs

- requires pre-processing
- user input must be merged manually
- less “chat-like”

---

## 2. State-Based Memory

### Description

Memory is a summarized state, not chat history.

Example state:
- user preferences
- long-term facts
- active goals

### Why it works

Because:
- signal strength stays high
- old noise is removed
- memory behaves predictably

### Trade-offs

- requires summarization logic
- loses conversational flavor
- cannot reconstruct dialogue

---

## 3. Minimal Grammar

### Description

Use strict output format only when required.

Prefer:
- loose structure
- soft markers
- human-readable text

### Why it works

Because:
- format pressure is reduced
- semantic richness is preserved
- language drift decreases

### Trade-offs

- harder to parse
- requires downstream validation
- less deterministic

---

## 4. Local Language Trigger

### Description

Language instruction placed near the end,
inside the final User message.

### Why it works

Because:
- recency activates language
- dominance favors local rules
- global language rules decay

### Trade-offs

- not guaranteed
- fails under heavy format pressure
- probabilistic by nature

---

## 5. One Decision Point

### Description

The model is asked to make one decision per turn.

Not:
- reason + classify + format + translate

But:
- do exactly one thing

### Why it works

Because:
- constraint competition is minimized
- attention is focused
- instruction load stays low

### Trade-offs

- requires orchestration outside the model
- more API calls
- less “all-in-one” behavior

---

## 6. Minimal Rule Set

### Description

Less than 8 independent rules.

No overlapping constraints.

### Why it works

Because:
- dominance remains stable
- fewer conflicts
- easier debugging

### Trade-offs

- weaker guarantees
- more edge cases
- less expressiveness

---

## 7. Stateless Core + External Control

### Description

The prompt itself stays simple.

Control is implemented via:
- validation
- retries
- filters
- routing logic

### Why it works

Because:
- prompts are not forced to do everything
- complexity is handled deterministically
- failure is observable

### Trade-offs

- requires engineering effort
- not “prompt-only”
- higher system complexity

---

## Mental model

Good prompt architecture is not:
more instructions.

It is:
fewer, clearer dominance paths.

Patterns optimize for:
- stability over cleverness
- predictability over power
- subtraction over addition
