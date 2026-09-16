# 1. Route Planning (Greedy Best-First Search)

## Problem Statement
Find an efficient travel route between an origin city and a destination city using straight-line distance estimates to guide the agent toward the goal.

### Evaluation Function
$$f(n) = h(n)$$
* $h(n)$: The estimated remaining straight-line distance (heuristic) from city $n$ directly to the target city.

### Strategy & Algorithm
1. **State Representation:** The current city and the list of visited intermediate cities.
2. **Priority Expansion:**
   - Maintain a min-priority queue sorted strictly by $h(n)$.
   - Extract the node that appears closest to the target destination according to the heuristic table.
   - Check adjacent roads/cities; push unvisited neighbors into the priority queue alongside their updated paths.
3. **Termination:** Stop when the destination city is popped from the queue.

### Learning Takeaways
* Demonstrates informed search where domain knowledge (heuristics) prunes the search space.
* Fast and goal-directed, though not guaranteed to find the shortest total driving route because it ignores accumulated travel cost $g(n)$.

---

# 2. 8-Puzzle Problem (A* Search)

## Problem Statement
Transform a scrambled $3 \times 3$ sliding tile puzzle into the standard goal configuration `(1, 2, 3, 4, 5, 6, 7, 8, 0)` using the minimum number of sliding moves.

### Evaluation Function
$$f(n) = g(n) + h(n)$$
* $g(n)$: The exact cost incurred so far (number of steps from the initial configuration).
* $h(n)$: The sum of Manhattan distances $\sum (|x_1 - x_2| + |y_1 - y_2|)$ of all non-blank tiles from their intended target positions.

### Strategy & Algorithm
1. **State Representation:** A flat 9-element tuple representing the board, with `0` marking the empty slot.
2. **A* Search Loop:**
   - Insert the initial board into a min-priority queue prioritized by $f(n)$.
   - Pop the state with the lowest $f(n)$ value.
   - If it matches the goal layout, reconstruct and return the full step sequence.
   - Generate valid successor states by swapping `0` with its adjacent horizontal or vertical neighbors.
   - For each valid neighbor, compute $g(n) + h(n)$ and enqueue if it offers a shorter path than previously recorded.

### Learning Takeaways
* Illustrates how an admissible heuristic (Manhattan distance never overestimates true remaining cost) guarantees an optimal solution.
* Balances greedy exploration with path cost to avoid suboptimal paths.