# 1. Maze Solver (Breadth-First Search)

## Problem Statement
Navigate an agent through a 2D binary maze from a specified starting coordinate to a goal exit tile, where `0` represents an open, walkable path and `1` represents an impassable obstacle or wall.

### Strategy & Algorithm
1. **State Representation:** A coordinate pair `(row, col)` indicating the current grid cell.
2. **Exploration Loop:**
   - Store active candidate paths inside a standard FIFO queue.
   - Dequeue the oldest path and inspect the current head cell.
   - Explore all valid adjacent cells (Up, Down, Left, Right) that are within bounds, clear of walls (`0`), and unvisited.
   - Enqueue the extended paths and record newly discovered cells in a `visited` set to avoid infinite cycles.
3. **Termination:** The search halts the instant the goal coordinate is reached.

### Learning Takeaways
* Demonstrates uninformed (blind) systematic search over a discrete 2D grid.
* Guarantees the optimal, shortest path in unweighted environments because it expands radially layer by layer.

---

# 2. Graph Traversal (Depth-First Search)

## Problem Statement
Systematically visit every reachable node in an arbitrary network by moving as deep as possible along each branch before backtracking.

### Strategy & Algorithm
1. **State Representation:** A node label/identifier within an adjacency list representation.
2. **Recursive Traversal Loop:**
   - Mark the current node as visited and record it in the traversal sequence.
   - Iterate through every adjacent neighbor listed in the graph.
   - If a neighbor has not yet been visited, recursively trigger the traversal on that neighbor.
   - Backtrack automatically via the call stack once all outgoing edges from a branch are exhausted.

### Learning Takeaways
* Demonstrates memory-efficient, LIFO-style graph exploration without needing to retain full frontier levels in memory.
* Shows how recursion naturally provides a backtracking mechanism for path and tree exploration.