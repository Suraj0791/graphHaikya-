




# PHASE 0

## Why Do Cycles Matter?

Before algorithms.

Questions like

> Why is a cycle even a problem?

Examples

```
DependenciesA needs BB needs CC needs AImpossible.
```

Real-world intuition.

---

# PHASE 1

## What Is A Cycle?

Not graph theory.

Physics.

We'll derive

```
Path↓Loop↓Returning↓Infinite Walk↓Cycle
```

---

# PHASE 2

## Why DFS Can Detect Cycles

This is the heart.

Question.

Why can DFS detect something that BFS doesn't naturally detect?

We'll derive from

```
Current recursion path
```

This is where the magic begins.

---

# PHASE 3

## The Gray State

NOT

"Gray means visiting."

Instead

We'll answer

> **Why does GRAY exist?**

This chapter alone will kill the mystery.

We'll derive

```
White↓Gray↓Black
```

Not memorize.

Derive.

---

# PHASE 4

## Back Edge

Question.

What exactly is a back edge?

Why does

```
Gray↓Gray
```

mean cycle?

We'll prove it.

---

# PHASE 5

## Directed Graph Cycle Detection

Now code becomes trivial.

---

# PHASE 6

## Undirected Graph

Question.

Why does Gray suddenly fail?

Why do we suddenly need Parent?

This confuses thousands of people.

We'll derive it.

---

# PHASE 7

## Parent Edge

Not code.

Why should parent edge be ignored?

Huge chapter.

---

# PHASE 8

## Invariants

Like BFS.

We build

Cycle Detection invariant.

---

# PHASE 9

## Universal Template

Now code.

---

# PHASE 10

## Pattern Recognition

Questions.

```
Course Schedule↓Can Finish↓Find Cycle↓Safe States
```

Recognition.

---

# PHASE 11

## Decision Tree

Exactly like BFS.






Tree Algorithms
│
├── LCA Bible
├── Tree DP Bible
└── Tree Pattern Book

↓

Shortest Paths
│
├── Dijkstra
├── Bellman-Ford
├── Floyd-Warshall
├── Johnson
└── Shortest Path Pattern Book

↓

Connectivity
│
├── DSU
├── Kruskal
├── Prim
└── Connectivity Pattern Book

↓

Graph Modeling Bible

↓

Graph Operating System





# First Law of Cycle Detection

A cycle is not dangerous because it is a circle.

A cycle is dangerous because

> **something depends on itself before it has finished.**

Read that again.

This sentence is more important than the definition.




A cycle is

> **Trying to enter a world that is still being explored.**

Not

"a loop."

Not

"repeated node."

Much deeper.

---



Did you catch that?

The problem is NOT

visiting again.

The problem is

visiting again

**before finishing.**