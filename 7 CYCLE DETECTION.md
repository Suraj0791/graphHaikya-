




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


# Dependency Pattern Book

We'll take **8–10 carefully selected problems** and compress them into one recognition system.

Examples:

- Course Schedule I
- Course Schedule II
- Alien Dictionary
- Sequence Reconstruction
- Eventual Safe States (interesting bridge back to cycle detection)
- Build Order
- Parallel Courses
- Recipes from Supplies



The goal will be:

> **See "dependency / prerequisite / before-after / build order" → immediately recognize whether the interviewer wants:**
> 
> - **Existence? → Cycle Detection**
> - **Actual order? → Topological Sort**




# The Right Way

Your brain should detect

**DEPENDENCIES.**

Not the problem.

The relationship.




# ecognition Rule #1

## One thing must happen BEFORE another.

Keywords.

```
BeforeAfterDepends onRequiresPrerequisiteMust finish firstMust complete first
```

Question.

What do all these mean?

They all secretly say

```
A↓B
```

An edge.

---

# Recognition Rule #2

## Build Order

Suppose interviewer says

```
Compile project.Some files depend on others.Find an order.
```

Question.

What's the real problem?

Not compiler.

Dependency graph.

---

# Recognition Rule #3

## Scheduling

Example.

```
TasksDependenciesOrder
```

Again.

Dependency graph.

---

# Recognition Rule #4

## Installation

Example.

```
Install package ANeeds library BNeeds library C
```

Again.

Dependency graph.

---

# Recognition Rule #5

## Courses

```
CoursePrerequisite
```

Again.

Dependency graph.

---

# BRO.

Notice.

The story changes.

The graph doesn't.

---

# The First Split

Once your brain detects

DEPENDENCY,

ask exactly ONE question.

```
Need to know...Can everything finish?ORNeed actual order?
```

That's it.




# The First Split

Once your brain detects

DEPENDENCY,

ask exactly ONE question.

```
Need to know...Can everything finish?ORNeed actual order?
```

That's it.

---

## Branch 1

Need only

```
Possible?
```

Question examples.

```
Can finish all courses?Is dependency valid?Cycle exists?Can project compile?
```

Answer.

```
Cycle Detection
```

Not Topo.

---

## Branch 2

Need

```
Give me an order.
```

Examples.

```
Return course orderBuild orderTask scheduleInstall sequence
```

Answer.

```
Topological Sort
```

---

```
Dependency?

↓

YES

↓

Need what?

──────────────

Can finish?

↓

Cycle Detection

──────────────

Need actual order?

↓

Topological Sort
```




# The Dependency Graph Family

|English|Meaning|
|---|---|
|Before|Dependency|
|After|Dependency|
|Requires|Dependency|
|Prerequisite|Dependency|
|Depends On|Dependency|
|Build Order|Dependency|
|Install Order|Dependency|
|Compilation Order|Dependency|
|Task Scheduling|Dependency|

Different stories.

One graph.






# Pattern 1 — Existence

## Recognition

Question is asking

> **Can everything finish?**

NOT

Give order.

Keywords

```
Possible?Can Finish?Valid?Cycle?Deadlock?Dependency valid?
```

Engine

```
Cycle Detection
```

---

## Problem 1

### Course Schedule I ⭐⭐⭐⭐⭐

This is THE problem.

Everything begins here.

After solving this,

you understand

```
Dependency↓Directed Graph↓Need only existence↓Cycle Detection
```

---

## Problem 2

### Detect Cycle in Directed Graph

Same engine.

Different wording.

Nothing new.

---

## Problem 3

### Detect Cycle in Undirected Graph

Only plugin changes.

Parent.

Nothing else.

---

# Pattern 2 — Ordering

Recognition

Need actual order.

Keywords

```
Return orderScheduleBuild orderInstallation orderCompilation order
```

Engine

```
Topological Sort
```

---

## Problem 4

### Course Schedule II ⭐⭐⭐⭐⭐

Same graph.

Same dependencies.

Only output changes.

Instead of

```
Possible?
```

Now

```
Give order.
```

One tiny twist.

Huge interview favorite.

---

## Problem 5

### Build Order

Literally Course Schedule.

Different story.

---

# Pattern 3 — Modeling

Now interviewer hides the graph.

---

## Problem 6

### Alien Dictionary ⭐⭐⭐⭐⭐

This is NOT difficult because of Topological Sort.

It's difficult because

you have to **build the graph first**.

New skill.

Graph Modeling.

Same engine.

---

## Problem 7

### Recipes From Supplies

Again.

Hidden dependency graph.

Same engine.

---

# Pattern 4 — Safe Nodes

Now comes a beautiful bridge.

---

## Problem 8

### Find Eventual Safe States ⭐⭐⭐⭐⭐

This deserves special attention.

Because your brain will initially think

```
Cycle Detection
```

But the question is subtly different.

It asks

> **Which nodes are guaranteed NOT to reach a cycle?**

This becomes a bridge to future graph ideas (reverse graphs, outdegree/Kahn approach, etc.).

---

# Pattern 5 — Advanced Dependency

---

## Problem 9

### Parallel Courses

Scheduling.

Dependencies.

Sometimes asks for levels instead of just an order.

Bridge between Topo and BFS.

---

## Problem 10

### Sequence Reconstruction

This is the hardest in this family.

Now you're not only checking whether a topological order exists.

You're checking whether it is **unique**.

Beautiful extension of the "multiple topological orders" concept we proved in the Bible.

---

# The Compression Sheet

I want your brain to reduce all 10 problems into this:

```
Read Problem      │      ▼Do I see dependencies?      │      ▼YES      │      ▼What is being asked?
```

---

### Branch 1

```
Can everything finish?↓Cycle Detection
```

Representative Problems

- Course Schedule I
- Directed Cycle
- Undirected Cycle

---

### Branch 2

```
Need execution order?↓Topological Sort
```

Representative Problems

- Course Schedule II
- Build Order

---

### Branch 3

```
Need to build graph first?↓Graph Modeling↓Topo / Cycle
```

Representative Problems

- Alien Dictionary
- Recipes

---

### Branch 4

```
Need safe nodes?↓Cycle reasoning
```

Representative Problem

- Eventual Safe States

---

### Branch 5

```
Need uniqueness?↓Advanced Topological reasoning
```

Representative Problem

- Sequence Reconstruction

---

# Interview Recognition OS

By now, your brain should automatically do this:

```
Dependency words?(before, after, prerequisite, depends on,requires, build order, install order)        │        ▼Dependency Graph        │        ▼Need what?──────────────Validity?↓Cycle Detection──────────────Ordering?↓Topological Sort──────────────Graph hidden?↓Model Graph↓Then Cycle / Topo──────────────Unique order?↓Advanced Topological
```

---

# 📍Current Status of the Graph Universe

```
✅ Graph Physics✅ BFS Bible✅ BFS Pattern Book✅ DFS Core Bible✅ Cycle Detection Bible✅ Topological Sort Bible✅ Dependency Pattern Book━━━━━━━━━━━━━━━━━━━━━━━NEXT━━━━━━━━━━━━━━━━━━━━━━━📖 Euler Tour Bible
```