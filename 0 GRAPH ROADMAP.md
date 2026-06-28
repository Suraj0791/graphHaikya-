
# Graph Universe

The goal is to have the same feeling you had after the BFS Bible:

> "I know exactly where I am, what comes next, and why."

---

# The Graph Universe

Think of Graphs as an **Operating System**, not just a collection of algorithms.

```
GRAPH UNIVERSE

            GRAPH PHYSICS
                  │
      ┌───────────┴───────────┐
      │                       │
GRAPH EXPLORATION      GRAPH OPTIMIZATION
      │                       │
      │                       │
DFS / BFS              Shortest Path / MST
      │
      ▼
ADVANCED DFS WORLD
      │
      ▼
GRAPH OPERATING SYSTEM
```

Everything fits somewhere.

---

# Part 0 — Graph Physics (Foundation)

Before learning algorithms, understand the fundamentals.

```
Graph
    ↓
Node
    ↓
Edge
    ↓
Directed / Undirected
    ↓
Weighted
    ↓
Cycle
    ↓
Connected Component
    ↓
Tree
    ↓
Forest
    ↓
DAG
    ↓
State Graph
    ↓
Grid Graph
```

This foundation is basically complete.

---

# Part 1 — BFS Universe ✅

Completed.

```
BFS Physics
    ↓
Wave
    ↓
Layer
    ↓
Queue
    ↓
State
    ↓
Transition
    ↓
Visited
    ↓
Plugins
    ↓
Operating System
    ↓
Pattern Book
```

Done.

---

# Part 2 — DFS Universe (Current)

This is much bigger than BFS.

## Phase A — DFS Physics ✅

Completed.

```
Why DFS
    ↓
Stack
    ↓
Recursion
    ↓
Entry
    ↓
Exit
    ↓
Gray
    ↓
Responsibility
    ↓
Engine
    ↓
Plugins
    ↓
Operating System
```

Done.

---

## Phase B — DFS Pattern Book

Now comes the interview preparation.

The goal is no longer theory.

The goal is recognizing patterns.

---

### Pattern 1 — Traversal

```
Connected Components
        ↓
Number of Islands
        ↓
Flood Fill
        ↓
Provinces
        ↓
Reachability
        ↓
Surrounded Regions
        ↓
Max Area of Island
```

---

### Pattern 2 — Top Down

```
Depth
    ↓
Path Sum
    ↓
Root to Leaf
    ↓
Prefix Sum
    ↓
Distance
    ↓
Binary Tree Paths
```

---

### Pattern 3 — Bottom Up

The biggest pattern.

```
Height
    ↓
Diameter
    ↓
Balanced Tree
    ↓
Maximum Path Sum
    ↓
Subtree Sum
    ↓
Subtree Size
    ↓
Largest BST
    ↓
House Robber III
    ↓
Tree DP Introduction
```

---

### Pattern 4 — Backtracking

```
Subsets
    ↓
Permutations
    ↓
Combination Sum
    ↓
Generate Parentheses
    ↓
Sudoku
    ↓
N Queens
    ↓
Rat in Maze
```

By the end of this section, you won't memorize these problems.

You'll recognize them.

---

# Part 3 — DFS Advanced Plugins

Each of these is **not** a random algorithm.

Each is simply a plugin on top of the DFS engine.

---

## Plugin 1 — Cycle Detection Bible

```
Why Gray?
    ↓
Back Edge
    ↓
Directed
    ↓
Undirected
    ↓
Recursion Stack
    ↓
Parent Edge
```

---

## Plugin 2 — Topological Sort Bible

```
Why Finish Time?
        ↓
Exit Plugin
        ↓
Reverse Order
        ↓
DAG
        ↓
Kahn vs DFS
        ↓
Applications
```

---

## Plugin 3 — Euler Tour Bible

One of the coolest concepts.

```
Entry Time
      ↓
Exit Time
      ↓
Flatten Tree
      ↓
Subtree Interval
      ↓
Euler Array
      ↓
Prefix Queries
```

---

## Plugin 4 — Low Link Bible

Probably the hardest concept in graphs.

```
Discovery Time
        ↓
Back Edge
        ↓
Low[]
        ↓
Bridge
        ↓
Articulation
        ↓
Tarjan Foundation
```

---

## Plugin 5 — SCC Bible

```
Strongly Connected
        ↓
Component Graph
        ↓
Kosaraju
        ↓
Tarjan SCC
        ↓
Condensation DAG
```

---

## Plugin 6 — Tree DP Bible

```
Return State
      ↓
Merge
      ↓
Include
      ↓
Exclude
      ↓
Re-rooting
      ↓
DP on Trees
```

---

## Plugin 7 — LCA Bible

```
Naive
   ↓
Euler
   ↓
RMQ
   ↓
Binary Lifting
   ↓
Queries
```


# Part 4 — Shortest Path Universe

A completely different family of graph algorithms.

The objective is no longer exploration.

The objective is **finding optimal paths**.

---

## Bible 1 — Dijkstra Bible

Understand:

```
Why Greedy?
      ↓
Relaxation
      ↓
Priority Queue
      ↓
Invariant
      ↓
Plugins
      ↓
Recognition
```

Then move to the Pattern Book.

### Pattern Book

```
Network Delay Time
      ↓
Minimum Effort Path
      ↓
Cheapest Flights
      ↓
Maze
      ↓
State Dijkstra
```

---

## Bible 2 — Bellman-Ford Bible

Understand:

```
Relaxation
      ↓
Negative Edge
      ↓
Negative Cycle
      ↓
Proof
      ↓
Recognition
```

---

## Bible 3 — Floyd-Warshall Bible

Understand:

```
Intermediate Node
      ↓
DP Thinking
      ↓
Transitive Closure
      ↓
All Pairs Shortest Path
```

---

## Bible 4 — Johnson's Algorithm

The bridge between shortest-path algorithms.

Useful for sparse graphs with negative edges.

---

# Part 5 — MST Universe

Minimum Spanning Tree.

---

## DSU Bible

Understand:

```
Component
      ↓
Union
      ↓
Find
      ↓
Path Compression
      ↓
Union by Rank
      ↓
Proof
```

### DSU Pattern Book

```
Redundant Edge
      ↓
Accounts Merge
      ↓
Number of Islands II
      ↓
Dynamic Connectivity
```

---

## Kruskal Bible

Understand:

```
Why Sort?
      ↓
Safe Edge
      ↓
Cut Property
      ↓
DSU Plugin
```

---

## Prim Bible

Understand:

```
Growing Tree
      ↓
Greedy
      ↓
Priority Queue
      ↓
Dense vs Sparse
```

---

# Part 6 — Graph DP Universe

## DAG DP Bible

```
Longest Path
      ↓
Counting Paths
      ↓
Course Schedule
      ↓
Scheduling
      ↓
Dependency DP
```

---

# Part 7 — Graph Modeling Bible

This is what separates average candidates from strong problem solvers.

Most "hard graph problems" are actually **wrong graph models**.

Learn how to model:

```
Grid
      ↓
State Space
      ↓
Bitmask Graph
      ↓
Implicit Graph
      ↓
Complement Graph
      ↓
Line Graph
      ↓
Tree as Graph
```

Modeling is often harder than coding.

---

# Part 8 — Graph Recognition Bible

This becomes your decision-making Operating System.

```
Need shortest path?
      ↓
Weighted?
      ↓
Negative edges?
      ↓
All pairs?
      ↓
Need connectivity?
      ↓
Dynamic connectivity?
      ↓
Need ordering?
      ↓
Need SCC?
      ↓
Need bridge?
      ↓
Need subtree?
      ↓
Need traversal?
```

One decision tree.

One operating system.

---

# Part 9 — Graph Interview Bible

This is the final boss.

Not algorithms.

Thinking.

```
How to identify graph?
      ↓
How to model?
      ↓
How to choose algorithm?
      ↓
Complexity estimation
      ↓
Optimization
      ↓
Edge cases
      ↓
Interview heuristics
```



