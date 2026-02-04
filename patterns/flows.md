```mermaid
flowchart TD
  %% =========================
  %% Prompt Engineering Patterns — Master Map
  %% =========================

  P0["PATTERNS: Stable Prompt Architectures
Goal: reduce drift, reduce conflicts, keep dominance stable"] --> P1
  P0 --> P2
  P0 --> P3
  P0 --> P4
  P0 --> P5
  P0 --> P6
  P0 --> P7

  %% --- Pattern 1
  subgraph P1["1) Single-User Pattern"]
    P1a["One User message per turn
(state + context + task merged)"] --> P1b["One decision point"]
    P1b --> P1c["Stable recency dominance"]
    P1c --> P1d["Less random rule drops"]
  end

  %% --- Pattern 2
  subgraph P2["2) State-Based Memory"]
    P2a["Memory is state summary
(not raw chat history)"] --> P2b["Overwrite each turn
(no accumulation)"]
    P2b --> P2c["High signal / low noise"]
    P2c --> P2d["More predictable behavior"]
  end

  %% --- Pattern 3
  subgraph P3["3) Minimal Grammar"]
    P3a["Use the weakest structure that works
(avoid strict schemas when possible)"] --> P3b["Lower format pressure"]
    P3b --> P3c["Higher semantic richness"]
    P3c --> P3d["Lower language drift risk"]
  end

  %% --- Pattern 4
  subgraph P4["4) Local Language Trigger"]
    P4a["Language rule near end
inside final User"] --> P4b["Recency activation"]
    P4b --> P4c["Higher probability of correct language"]
    P4c --> P4d["Less mixing under mild pressure"]
  end

  %% --- Pattern 5
  subgraph P5["5) One Decision Point"]
    P5a["Ask the model to do one thing per turn
(not classify + reason + format + translate)"] --> P5b["Lower constraint competition"]
    P5b --> P5c["More stable output"]
    P5c --> P5d["Easier debugging"]
  end

  %% --- Pattern 6
  subgraph P6["6) Minimal Rule Set"]
    P6a["< 8 independent rules
(no overlapping constraints)"] --> P6b["Stable dominance"]
    P6b --> P6c["Fewer conflicts"]
    P6c --> P6d["Less drift over time"]
  end

  %% --- Pattern 7
  subgraph P7["7) Stateless Core + External Control"]
    P7a["Keep prompt core simple"] --> P7b["Move guarantees outside prompt
(validation / retries / routing)"]
    P7b --> P7c["Deterministic control layer"]
    P7c --> P7d["Prompt stops growing endlessly"]
  end

  %% =========================
  %% How patterns reinforce each other
  %% =========================

  P1d --> R["RESULT: Lower entropy systems
more predictable, less fragile"]

  P2d --> R
  P3d --> R
  P4d --> R
  P5d --> R
  P6d --> R
  P7d --> R

  %% Reinforcement links
  P6a --> P1a
  P6a --> P3a
  P5a --> P6a
  P2a --> P1a
  P3a --> P4a

  %% Pressure/Tradeoff notes (kept inside diagram)
  R --> T1["Tradeoff: fewer guarantees
prompt-only cannot enforce correctness"]
  R --> T2["Tradeoff: less structure
may require downstream parsing/validation"]
  R --> T3["Tradeoff: memory is lossy
state summary loses conversational detail"]
