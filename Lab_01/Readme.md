# 1. Vacuum Cleaner Problem

## Problem Statement
A simple reflex agent cleans an environment consisting of two rooms (`A` and `B`). Each room can be either `Clean` or `Dirty`.

### Production Rules
1. **Rule 1 (Cleaning):** If current room is `Dirty` $\rightarrow$ Action: `SUCK`.
2. **Rule 2 (Movement A $\to$ B):** If current room is `A` and `Clean` $\rightarrow$ Action: Move `RIGHT`.
3. **Rule 3 (Movement B $\to$ A):** If current room is `B` and `Clean` $\rightarrow$ Action: Move `LEFT`.

### Learning Takeaways
* Demonstrates a pure reflex agent: actions depend solely on the current percept, requiring no past memory.
* Ideal for closed, fully observable, static worlds.

---

# 2. Water Jug Problem

## Problem Statement
Given two jugs of capacities $X$ and $Y$ with no measurement markings, measure exactly $Z$ liters of water.

### Solvability Condition
$Z \le \max(X, Y)$ and $Z \pmod{\gcd(X, Y)} = 0$.

### Intuitive Rule Loop
1. If Jug 1 is empty, **fill** it.
2. If Jug 2 is full, **empty** it.
3. Otherwise, **pour** water from Jug 1 into Jug 2 until Jug 2 is full or Jug 1 is exhausted.

### Learning Takeaways
* Demonstrates deterministic state manipulation where infinite capacity sources and sinks reduce continuous math to discrete steps.

---