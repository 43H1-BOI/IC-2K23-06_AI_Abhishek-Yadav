# 1. Missionaries and Cannibals Problem

## Problem Statement
Three missionaries and three cannibals must cross a river using a two-person boat. At no point on either riverbank may cannibals outnumber missionaries (otherwise, missionaries are eaten).

### State Representation
* State: `(M_left, C_left, boat)`
  * `M_left`: Missionaries on the starting bank ($0 \le M_{left} \le 3$).
  * `C_left`: Cannibals on the starting bank ($0 \le C_{left} \le 3$).
  * `boat`: `1` if boat is on the left bank, `0` if on the right bank.
* Start State: `(3, 3, 1)`
* Goal State: `(0, 0, 0)`

### Safety Invariant
For both sides of the river:
$$\text{If } M > 0 \implies M \ge C$$

### Learning Takeaways
* Introduces state constraints and pruning: states that violate safety are discarded immediately.
* Breadth-First Search (BFS) guarantees discovering the solution with the minimum number of boat trips (11 crossings).

---

# 2. Rule-Based Decision Making

## Problem Statement
An automated rule engine checks input symptoms/indicators against pre-programmed `IF-THEN` rules to classify a condition or issue recommendations.

### Working Principle
* **Knowledge Base:** Stores facts and rules.
* **Inference Engine:** Evaluates inputs, tests rule criteria, and triggers actions/conclusions (forward chaining).

### Learning Takeaways
* Basis of classical expert systems: cleanly separates domain knowledge from the execution engine.

---