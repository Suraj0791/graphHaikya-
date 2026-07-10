
```
GRAPH / TREE

↓

Need shortest path?

YES

↓

BFS Family

-----------------

NO

↓

Need complete exploration only?

↓

Traversal DFS

-----------------

Need information from parent?

↓

Top Down

-----------------

Need information from children?

↓

Bottom Up

-----------------

Need to try choices?

↓

Backtracking

-----------------

Need cycle detection?

↓

Gray State Plugin

-----------------

Need ordering after completion?

↓

Exit Time Plugin

↓

Topo Sort

-----------------

Need subtree intervals?

↓

Euler Tour Plugin

-----------------

Need bridge/articulation?

↓

Low Link Plugin
```




Think physically.

You entered A.

Never exited.

Entered B.

Never exited.

Entered C.

Never exited.

Now...

you're trying to enter A again.

Question.

How?

You're already inside A.

Impossible.





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





# The Deep Insight

DFS has two very different moments.

Remember the engine.

```
ENTER↓Explore↓EXIT
```

Question.

Can one boolean

represent both?

Impossible.

They're different events.




# Now Let's Name Them

Computer scientists chose

```
WHITENever Seen
```

---

```
GRAYEnteredNot Finished
```

---

```
BLACKFinished
```

Notice.




ENTER

↓

Child Loop

↓

EXIT



Now attach states.

WHITE

↓

ENTER

↓

GRAY

↓

Explore Children

↓

EXIT

↓

BLACK






# Why Gray Is Dangerous

Suppose current recursion is

```
A↓B↓C
```

Question.

What color are they?

All Gray.

Why?

Because none finished.

---

Suppose C points to A.

Question.

A's color?

Gray.

Question.

Meaning?

A is still unfinished.

Question.

Can DFS legally enter A again?

Impossible.

Because you're already inside A.

That impossibility

is exactly the cycle.

---

# Why Black Is Safe

Suppose instead

A already became Black.

Now another edge reaches A.

Question.

Problem?

No.

A's work is complete.

Nothing can loop back into unfinished work.




Remember this.

```
WHITE↓Never Entered
```

```
GRAY↓Between Entry and Exit
```

```
BLACK↓Already Exited
```

The colors disappear.

The engine remains.





Does DFS hate revisiting nodes?

No.

DFS only hates revisiting

unfinished nodes.

Huge difference.




BLACK?

Already finished.

Safe.

Go if the problem allows it.




GRAY?

Still inside recursion.

Danger.

Exactly one state is dangerous.

---




Books say

> Edge to ancestor.

I don't like it.

Here's the deeper version.

A Back Edge is

> **An edge that points to a node whose work is still unfinished.**

Notice.

Gray.

Not ancestor.

Ancestor is just a consequence.




> **Encountering a Gray node means the current DFS path has found a way back into itself before completing. Therefore a cycle exists.**




Today we proved three profound ideas:

1. **Gray nodes are exactly the active recursion stack.**
2. **A back edge is simply an edge into unfinished work.**
3. **Cycles are not "loops"; they are unfinished work depending on itself.**



Directed → Gray

Undirected → Parent




# Why Does Gray Suddenly Fail in Undirected Graphs?

---

## STOP.




Undirected Graph Rule

> **Gray is dangerous only if it is NOT the parent.**




# The Fundamental Difference

Directed Graph

Every edge has meaning.

```
A → B
```

does NOT imply

```
B → A
```

So seeing Gray

is surprising.

---

Undirected Graph

Every edge appears twice.

```
A → BandB → A
```

Therefore

seeing parent

is expected.

Not surprising.



dekho in directed graph bhai if u find a gray node it sure its  new node not parent node , but in undireected graph ther ia  cocnept of parent i mean a-> b nd b-> a exist so id we go from a to b nd then b see a again but is gray but thsi i not a new this is parent this was sure to exit 



## Directed

Question.

Gray?

Cycle.

Done.

Because every edge is meaningful.

---

## Undirected

Question.

Gray?

Wait.

Is it parent?

YES

↓

Ignore.

NO

↓

Cycle.




# The Invariant

Directed:

> Every edge to a Gray node points back into unfinished work.

Undirected:

> Every node naturally sees its parent again, so only a Gray node that is **not** the parent proves a cycle.

Notice how the invariant changed slightly—not the engine.

The DFS engine is still exactly the same





# What is our REAL job?

Not

> Detect cycle.

Much deeper.

Our job is

> **Never allow DFS to enter an unfinished world.**

Everything else follows.





We already built this.

```
ENTER↓Explore Children↓EXIT
```

Question.

Where can a cycle possibly happen?

At ENTER?

Impossible.

You're just entering.

---

At EXIT?

Impossible.

You're already done.

---

Then where?

Only here.

```
ENTER↓Explore Neighbor  ← ONLY HERE↓EXIT
```

Interesting.

Cycle detection only exists inside the child loop.

Not before.

Not after.

---

# The Guard

Imagine DFS has a security guard.

Every time we see a neighbor.

The guard asks one question.

```
Can I legally enter?
```

That's it.

Not

"Is there a cycle?"

Just

"Can I enter?"




# There are only THREE answers

Neighbor is

WHITE

```
Never entered.
```

Safe.

Go.

---

Neighbor is

GRAY

Question.

Can we enter?

No.

Already occupied.

Danger.

---

Neighbor is

BLACK

Question.

Need to enter?

Usually no.

Already finished.

Nothing to do.

---

BRO.

Cycle detection isn't detecting cycles.

It's actually an **admission policy**.

Think about that.





Every neighbor must pass inspection.

```
WHITE↓Enter
```

---

```
GRAY↓Reject
```

---

```
BLACK↓Ignore
```





## Directed Plugin

Question.

GRAY?

Reject immediately.

Done.

---

## Undirected Plugin

Question.

GRAY?

Wait.

Is it parent?

YES

↓

Expected.

Ignore.

---

NO

↓

Reject.

Cycle.




Directed Graph.

```


bool dfs(int node) {

    color[node] = GRAY;

    for (int nbr : graph[node]) {

        if (color[nbr] == WHITE) {
            if (dfs(nbr))
                return true;
        }

        else if (color[nbr] == GRAY) {
            return true;      // unfinished world found
        }
    }

    color[node] = BLACK;

    return false;
}
```




**undirected graph** using DFS

```
bool dfs(int node, int parent) {
    color[node] = GRAY;
    for (int nbr : graph[node]) {
        if (nbr == parent) {
            continue; // Skip the edge back to parent
        }
        if (color[nbr] == WHITE) {
            if (dfs(nbr, node)) return true;
        } else if (color[nbr] == GRAY) {
            return true; // Cycle found
        }
    }
    color[node] = BLACK;
    return false;
}

```




1. Directed Graph BFS (Cycle Detection)

In a directed graph, a cycle exists if you encounter a **GRAY** node while looking at neighbors. This means you found a path back to a node currently sitting in the queue. 

cpp

```
bool bfsDirected(int start, vector<vector<int>>& graph, vector<int>& color) {
    queue<int> q;
    
    q.push(start);
    color[start] = GRAY; // Gray means inside the queue
    
    while (!q.empty()) {
        int node = q.front();
        q.pop();
        
        for (int nbr : graph[node]) {
            if (color[nbr] == WHITE) {
                color[nbr] = GRAY; // Mark gray when pushing
                q.push(nbr);
            } else if (color[nbr] == GRAY) {
                return true; // Cycle found (back edge to a node in queue)
            }
            // BLACK neighbors are safely ignored
        }
        color[node] = BLACK; // Fully processed
    }
    return false;
}
```

Use code with caution.

Undirected Graph BFS (Cycle Detection)

For undirected graphs, encountering a **GRAY** node also means a cycle, _unless_ that gray node is the immediate parent that just discovered the current node. You must track parents using a map or array

cpp

```
bool bfsUndirected(int start, vector<vector<int>>& graph, vector<int>& color, vector<int>& parent) {
    queue<int> q;
    
    q.push(start);
    color[start] = GRAY;
    parent[start] = -1; // Root node has no parent
    
    while (!q.empty()) {
        int node = q.front();
        q.pop();
        
        for (int nbr : graph[node]) {
            if (nbr == parent[node]) {
                continue; // Skip the edge back to the parent
            }
            
            if (color[nbr] == WHITE) {
                color[nbr] = GRAY;
                parent[nbr] = node; // Track who pushed this neighbor
                q.push(nbr);
            } else if (color[nbr] == GRAY) {
                return true; // Cycle found (cross edge to a node in queue)
            }
        }
        color[node] = BLACK;
    }
    return false;
}
```


Summary of Differences

|Graph Type|Gray Neighbor Meaning|Action Needed|
|---|---|---|
|**Directed**|Always indicates a cycle|None, return `true` immediately|
|**Undirected**|Cycle _only_ if neighbor \(\ne \) parent|Track parents using a `parent` array|

---


Here's the question:

> **What does it actually mean when a graph has no cycles?**

Not "it's acyclic."

That's a definition.

I mean philosophically.

If there are no cycles...

what guarantee has the graph suddenly given us?

That guarantee is exactly what Topological Sort exploits






A cycle doesn't merely create a loop.

It destroys

the possibility of ordering.

Read that again.



# The First Law of DAGs

A cycle means

```
No valid order exists.
```

That's much deeper than

"Cycle detected."




When DFS detects a cycle,

it is actually proving

something much bigger.

It is proving

> **No complete execution order is possible**



A cycle is not

```
Geometry.
```

It is

```
Impossible completion.
```




Question.

What are they REALLY asking?

Not

"Find cycle."

They're asking

> **Can everything eventually finish?**



Your brain should immediately ask

> "Is a valid completion order even possible?"

Not

> "Should I use DFS?"

That's a consequence.




Cycle Detection asked

> **Can everyone finish?**

Topological Sort asks

> **If everyone CAN finish, in what order should they finish?**




They're the same story.

One says

Impossible.

The other says

Here's the order.





TOPO SORT ONLY WOKRS ON DIRECTED ACYCLIC GRAPH 
DIRECTED 





# The Meaning of an Edge

Forget

```
A → B
```

as a graph.

Read it in English.

It means

> **A must happen before B.**

Or

> **B depends on A.**

That's it.




# BOOM.

A New Question Is Born

Cycle Detection answered

```
Can everyone finish?
```

Now we ask

```
If everyone CAN finish...what should the order be?
```

That is literally the birth of Topological Sort.

Not a new algorithm.

A continuation of the previous Bible.




Topological Sort isn't magic.

It's simply

> **The reverse of the order in which DFS proves tasks are complete.**

Read that again.

That sentence alone explains the whole algorithm




We don't want

finish order.

We want

execution order.

Execution is the reverse of completion.

