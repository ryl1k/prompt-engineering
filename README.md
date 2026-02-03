# Prompt Engineering Field Guide (Prompt-Only)

### This repository is not about “how to write good prompts”.

### It is about:
- what people don’t see when working with LLMs,
- why “perfect prompts” still fail,
- how message order dominates outcomes,
- how memory actually works without a backend,
- why language control is probabilistic,
- and where most prompt engineering intuition is simply wrong.

### **Scope:** prompt-only.  
No external validation, no retries, no tools, no backend logic.  
Just the raw request sent to a model.

### The goal is to maximize instruction-following probability using only the prompt.

---

## What this repo is

This is a field guide for engineers who already:
- understand system / user / assistant roles,
- know about RAG, memory, schemas,
- and still see their prompts fail in production.

It focuses on:
- real failure modes,
- statistical behavior of LLMs,
- and practical constraints that are invisible in tutorials.

This is not:
- a beginner guide,
- a collection of “cool prompts”,
- or a marketing document.

---

## Core philosophy

LLMs do not execute rules.  
They generate the most statistically likely continuation of text.

Prompt engineering is not:
> writing better instructions

It is:
> shaping probability distributions under heavy constraints.

Most problems are not caused by:
- bad wording,
- or missing rules,

but by:
- message order,
- recency bias,
- instruction overload,
- conflicting constraints,
- and context placement.

---

## What you will find here

This repo documents patterns like:

- System prompts are not sandboxes, just biased prefixes.
- The last user message is the only real decision point.
- The middle of the context is almost dead.
- Raw chat history is not memory.
- Language control is never guaranteed.
- Markdown breaks because you didn’t define a grammar.
- More instructions often reduce compliance.
- “Always” and “Never” are meaningless tokens for LLMs.

Everything here is focused on:
**what actually happens, not what should happen.**

---

## How to use this repository

Start here:

1. `docs/01-roles-and-message-order.md`
2. `docs/03-recency-primacy-and-where-to-put-things.md`
3. `docs/04-memory-without-backend.md`
4. `docs/05-language-control-and-rtl.md`

Then use:
- `/templates` to build real prompt packs,
- `/tests` to run small sanity experiments,
- `/examples` for concrete prompt layouts.

---

## Design constraints

All techniques in this repo assume:

- one request → one response
- no external validators
- no repair loops
- no post-processing
- no tool calling

If a method requires backend logic, it does not belong here.

---

## Who this is for

This is for:
- AI engineers
- applied ML engineers
- people building real LLM products
- anyone who already knows the basics and is hitting limits

This is not for:
- “write me a prompt to…”
- beginners learning what a system prompt is
- people looking for magic phrases

---

## Mental model

Think less like:

> I am talking to an assistant

Think more like:

> I am shaping a stochastic text generator under strict constraints

Everything in this repo is written from that perspective.

---

## Disclaimer

Nothing here gives 100% guarantees.

Prompt engineering is probabilistic by nature.
All techniques shift probabilities, not certainties.

If you want guarantees, you need:
- validation,
- retries,
- or backend control.

This repo documents the maximum you can achieve
**before adding any of that.**
