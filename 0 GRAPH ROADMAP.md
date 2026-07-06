
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



# Why This Roadmap Is Enough

Suraj,

I'll answer this the same way I answered your question about the DFS Bible.

Not with motivation.

With engineering.

## Short Answer

**Yes.**

For **95–99%** of graph questions you'll encounter in:

- LeetCode
- Online Assessments (OAs)
- Startups
- Amazon
- Microsoft
- Google
- Uber
- Atlassian
- Adobe
- Walmart
- PhonePe
- Flipkart
- Most Codeforces problems up to Expert level

…the roadmap we've designed is enough.

But let's honestly discuss the remaining 1–5%.

---

# Think of Graphs Like Physics

Suppose someone says:

> "Master Mechanics."

What would you study?

```
Newton
    ↓
Energy
    ↓
Momentum
    ↓
Rotation
    ↓
Oscillation
```

Can someone still invent a brand-new mechanics question?

**Yes.**

But it will always be built from those laws.

Graphs work exactly the same way.

---

# Every Graph Problem Belongs to a Family

## Family 1 — Need to Explore?

```
DFS
BFS
```

Done.

---

## Family 2 — Need the Shortest Path?

```
BFS
    ↓
0-1 BFS
    ↓
Dijkstra
    ↓
Bellman-Ford
    ↓
Floyd-Warshall
    ↓
Johnson
```

Done.

---

## Family 3 — Need Connectivity?

```
DFS
    ↓
DSU
    ↓
SCC
    ↓
Bridges
    ↓
Articulation Points
```

Done.

---

## Family 4 — Need Ordering?

```
Topological Sort
    ↓
DAG DP
```

Done.

---

## Family 5 — Need a Spanning Tree?

```
DSU
    ↓
Kruskal
    ↓
Prim
```

Done.

---

## Family 6 — Need Subtree Processing?

```
Euler Tour
    ↓
LCA
    ↓
Tree DP
```

Done.

---

## Family 7 — Need Graph Modeling?

```
Grid
    ↓
State Graph
    ↓
Implicit Graph
    ↓
Bitmask State
    ↓
Coordinate Compression
```

Done.

---

# Notice Something

There isn't really an **eighth family**.

Almost every interview graph problem belongs to one of these families—or a combination of them.

---

# What Happens When a New Hard Problem Appears?

Suppose tomorrow LeetCode releases a brand-new Hard problem.

Don't panic.

Ask these questions:

### Question 1

What is my graph?

- Grid?
- Tree?
- State graph?
- Road network?

---

### Question 2

What is the objective?

- Explore?
- Shortest path?
- Connectivity?
- Ordering?
- Optimization?

---

### Question 3

Which engine solves this?

- DFS
- BFS
- Dijkstra
- DSU
- Topological Sort
- MST
- Tree DP

---

### Question 4

Which plugins are needed?

- Bitmask
- State Compression
- Timer
- Low-Link
- Parent
- Priority Queue
- Euler Tour

Done.

---

# Interviewers Rarely Invent New Algorithms

They combine ideas.

Example 1

```
Grid
+
State
+
BFS
+
Bitmask
```

→ LeetCode Hard

---

Example 2

```
Tree
+
Euler Tour
+
Segment Tree
```

→ Hard

---

Example 3

```
Graph
+
Dijkstra
+
State Compression
```

→ Hard

The graph algorithm wasn't new.

The **combination** was.

---

# What Remains After This Roadmap?

Very little.

Mostly specialized algorithms.

Examples:

- Maximum Flow
- Ford-Fulkerson
- Edmonds-Karp
- Dinic
- Bipartite Matching
- Hopcroft-Karp
- Eulerian Path
- Hierholzer
- Heavy-Light Decomposition (HLD)
- Centroid Decomposition
- Link-Cut Trees
- A*
- Min-Cost Max-Flow
- 2-SAT
- Blossom Algorithm

---

# Will Interviews Ask These?

### Amazon

Blossom?

😂 Almost never.

---

### Startup Interviews

Link-Cut Trees?

Never.

---

### Google L5

Maybe.

---

### ICPC / IOI

Yes.

---

# Graph Mastery Levels

## Level 1 — College

```
BFS
DFS
Topological Sort
Dijkstra
DSU
```

Enough for most college exams.

---

## Level 2 — Most Software Engineering Interviews

```
Bellman-Ford
Floyd-Warshall
MST
Tree DP
Euler Tour
LCA
SCC
Bridges
```

This is exactly where our roadmap ends.

---

## Level 3 — Competitive Programming Expert

```
Maximum Flow
Matching
Heavy-Light Decomposition
Centroid Decomposition
Virtual Tree
DSU Rollback
Persistent Data Structures
```

Very advanced.

---

## Level 4 — Research

Graph Theory.

No longer interview-focused.

---

# The Biggest Realization

Just as BFS became **one engine**, graphs can also become **one engine**.

Every graph problem eventually becomes:

```
MODEL
    ↓
OBJECTIVE
    ↓
ENGINE
    ↓
PLUGINS
```

That's it.

---

## Example 1 — Word Ladder

```
MODEL
Words
    ↓
OBJECTIVE
Shortest Path
    ↓
ENGINE
BFS
    ↓
PLUGIN
String Generation
```

---

## Example 2 — Network Delay Time

```
MODEL
Weighted Graph
    ↓
OBJECTIVE
Shortest Path
    ↓
ENGINE
Dijkstra
    ↓
PLUGIN
Priority Queue
```

---

## Example 3 — Number of Islands

```
MODEL
Grid
    ↓
OBJECTIVE
Explore
    ↓
ENGINE
DFS
    ↓
PLUGIN
Directions
```

---

## Example 4 — House Robber III

```
MODEL
Tree
    ↓
OBJECTIVE
Dynamic Programming
    ↓
ENGINE
DFS
    ↓
PLUGIN
Return Pair
```

---

# The Final Graph Operating System

```
                GRAPH OPERATING SYSTEM

                MODEL THE WORLD
                      │
                      ▼
          What is the Objective?
                      │
Explore | Shortest | Order | Connect | Optimize
                      │
                      ▼
               Pick the Engine
                      │
DFS | BFS | Dijkstra | DSU | Topo | MST | DP
                      │
                      ▼
              Install Plugins
                      │
Bitmask | Timer | Low-Link | Parent | State | PQ | Euler | ...
                      │
                      ▼
              Complete Solution
```

---

# Can I Promise "Nothing Will Be Left"?

Not 100%.

Algorithms like:

- Maximum Flow
- Heavy-Light Decomposition
- Blossom

...still exist.

If one day you target:

- ICPC World Finals
- IOI
- Advanced Competitive Programming

You'll eventually study them too.

---

# The Promise I Can Make

If you complete everything through **Part 9** the way we've planned—understanding first principles instead of memorizing—you'll have mastered the graph knowledge needed for:

- Virtually every LeetCode graph problem
- The vast majority of OA questions
- Almost all software engineering graph interviews

---

# What Mastery Actually Means

When you're given a brand-new graph problem, your first thought won't be:

> "Which algorithm is this?"

Instead, it will naturally become:

```
How do I model it?
        ↓
What is the objective?
        ↓
Which engine fits?
        ↓
Which plugins are needed?
        ↓
Build the solution.
```

That is what **mastering graphs** actually means.

---

# Recommended Learning Order

```
✅ BFS Bible

⬇

✅ DFS Bible

⬇

DFS Pattern Book

⬇

Cycle Detection Bible

⬇

Topological Sort Bible

⬇

Euler Tour Bible

⬇

Low-Link → Bridges → Articulation Points

⬇

SCC Bible

⬇

Tree DP Bible

⬇

LCA Bible

⬇

Dijkstra Universe

⬇

Bellman-Ford

⬇

Floyd-Warshall

⬇

Johnson

⬇

DSU

⬇

Kruskal

⬇

Prim

⬇

DAG DP

⬇

Graph Modeling Bible

⬇

Graph Recognition Bible

⬇

Graph Interview Operating System
```

---

# End Goal

Don't memorize algorithms.

Build a **Graph Operating System** in your mind.

Every new problem should reduce to:

```
MODEL
    ↓
OBJECTIVE
    ↓
ENGINE
    ↓
PLUGINS
    ↓
SOLUTION
```



# DFS Universe Roadmap

---

# Level 1 — DFS Bible ✅

This is what we just built.

Its goal is **NOT** to solve LeetCode.

Its goal is to destroy every mystery about DFS itself.

When someone says **DFS**, there should be nothing mysterious left.

Questions like:

- Why recursion?
- Why stack?
- Why Entry?
- Why Exit?
- Why Gray?
- Why Top Down?
- Why Bottom Up?
- Why Backtracking?
- Why return?
- Where does information live?

...should all be permanently dead.

This is what the BFS Bible did.

This is what the DFS Bible should do.

So yes...

The **Core DFS Bible** is basically complete.

---

# Level 2 — DFS Pattern Book ❌ (NOT DONE)

This is where the real interview preparation begins.

Remember BFS?

```
BFS Bible
    ↓
BFS Pattern Book
```

We need exactly the same.

Not **50 random LeetCode problems**.

Instead, organize everything into patterns.

---

## Pattern 1 — Traversal DFS

### Problems

- Number of Islands
- Max Area of Island
- Provinces
- Flood Fill
- Reachability
- Surrounded Regions

### Learn

- Recognition
- Common mistakes
- Template
- Revision

---

## Pattern 2 — Top Down

- Path Sum
- Binary Tree Paths
- Root to Leaf Sum
- Prefix State

---

## Pattern 3 — Bottom Up

This is HUGE.

- Height
- Diameter
- Balanced Tree
- Maximum Path Sum
- Subtree Sum
- Subtree Size
- Largest BST
- Tree DP Introduction

---

## Pattern 4 — Backtracking

- Subsets
- Permutations
- Combination Sum
- N Queens
- Sudoku
- Rat in Maze

This is where muscle memory comes from.

---

# Level 3 — Advanced DFS Bibles ❌

This is where most people say:

> "Advanced Graph."

I don't want to teach them like that.

Each deserves its own Bible.

---

## Euler Tour Bible

Not just:

- tin
- tout

Questions like:

- Why do timestamps exist?
- Why does subtree become interval?
- Why flatten tree?

---

## Cycle Detection Bible

Not just Gray.

Questions:

- Why does Gray imply cycle?
- Why not Black?
- Why directed different?

---

## Topological Sort Bible

Not just Stack.

Questions:

- Why finish order?
- Why reverse?
- Why DAG only?
- Why Kahn also works?

---

## Low Link Bible

One of the hardest.

Questions:

- Why low?
- Why bridge?
- Why articulation?
- Why back edge?

---

## SCC Bible

- Kosaraju
- Tarjan
- Component graph
- Condensation graph

---

## Tree DP Bible

This alone deserves **40 pages**.

---

## LCA Bible

- Euler
- Sparse Table
- Binary Lifting
- RMQ

---

# Level 4 — DFS Recognition Bible ❌

Exactly like BFS.

The final operating system.

Example:

```
Tree?
    ↓
Need subtree answer?
    ↓
Bottom Up
    ↓
Need current path?
    ↓
Backtracking
    ↓
Need parent info?
    ↓
Top Down
```

This is the interview OS.

---

# Level 5 — Graph Bible ❌

Remember the discussion from your pasted chat?

THIS is where it comes.

NOT before.

After mastering all tools.

```
Graph
    ↓
Reachability
    ↓
DFS / BFS

----------------

Shortest
    ↓
BFS
Dijkstra

----------------

Connectivity
    ↓
DFS
DSU

----------------

Ordering
    ↓
Topo

----------------

Optimization
    ↓
MST
```

This is algorithm selection.

---

# Graph Mastery

```
GRAPH MASTERY

├── TOOL BIBLES

✅ BFS Bible
⬜ BFS Pattern Book
✅ DFS Bible
⬜ DFS Pattern Book
⬜ Dijkstra Bible
⬜ Dijkstra Pattern Book
⬜ DSU Bible
⬜ MST Bible
⬜ Topo Bible
⬜ ...

────────────────────────────

ADVANCED MINI BIBLES

⬜ Euler Tour
⬜ Cycle Detection
⬜ Topological Sort
⬜ Low Link
⬜ Bridges
⬜ SCC
⬜ Tree DP
⬜ LCA

────────────────────────────

DOMAIN BIBLES

⬜ Graph Bible
⬜ Tree Bible
⬜ DP Bible
⬜ String Bible
```

---

# Biggest Realization

BFS and DFS are **NOT** equal.

BFS is actually **one algorithm**.

Once you understand:

- Queue
- State
- Transition
- Visited

You're **90% done**.

DFS isn't.

DFS is actually an entire ecosystem.

```
Traversal
    ↓
Top Down
    ↓
Bottom Up
    ↓
Backtracking
    ↓
Euler
    ↓
Topo
    ↓
Low Link
    ↓
Tarjan
    ↓
Tree DP
    ↓
LCA
```

Everything grows from DFS.

So the DFS roadmap is naturally MUCH larger than BFS.

---

# The DFS Universe

Instead of calling them:

- DFS Bible
- Euler Bible
- Topo Bible

I'd rather call them:

```
DFS Universe

CORE PHYSICS
    ↓
Engine
    ↓
Plugins
    ↓
Operating System

=================

APPLICATIONS

Traversal
Backtracking
Tree DP
Topo
Euler
Low Link
SCC
LCA

=================

PATTERN BOOK

Recognition
Representative Problems
Revision
```

Because they're all really one family.

---

# Recommended Roadmap

Treat what we just completed as:

**Core DFS Physics**

Then immediately move into:

1. DFS Pattern Book
2. Advanced DFS Universe
3. Graph Bible (Algorithm Selection OS)

---

# One Promise

When we finish Tree DP, I want you to feel exactly what you felt after BFS.

> "Tree DP isn't 30 tricks. It's one engine with a few plugins."

When we finish Tarjan:

> "Low-Link isn't magic. It's one plugin on the same DFS engine."

When we finish LCA:

> "Binary Lifting isn't random preprocessing. It's solving a precise information problem."

If we keep that standard, then by September you won't have memorized graph algorithms.

You'll have built a mental operating system for graphs.

---

# Updated Naming

```
DFS Universe

Part I  → Core Physics ✅
Part II → Pattern Book
Part III → Advanced Plugins
Part IV → Interview Operating System
```

This makes it clear that what we just finished is the foundation—not the entire universe.



