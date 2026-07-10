

# Phase 0

# What is my world?

First question.

```
What am I exploring?
```

There are only three common worlds.

```
Graph
Tree
Implicit State Space
```

Examples.

Graph

Cities

Roads

Friend Network

Course Schedule




State Space.

```
LockWord LadderPuzzleChessGameBitmask
```

Notice.

DFS engine doesn't care.

Everything becomes

```
Node+Edges
```

Exactly like BFS.




# Phase 1

# What is the objective?

THIS.

This is where chaos disappears.

Not

algorithm.

Objective.

---

Question.

What am I trying to achieve?

There are only a few families.

---

## Family 1

Need to simply explore?

```
Reachability

Connected Component

Island

Flood Fill
```

↓

Traversal Plugin.

---

## Family 2

Need information from parent?

Examples.

```
DepthRunning SumDistanceCurrent XORCurrent StringPath Prefix
```

↓

Top Down Plugin.

---

## Family 3

Need information from children?

Examples.

```
HeightDiameterSubtree SizeLargest BSTBalancedTree DP
```

↓

Bottom Up Plugin.

---

## Family 4

Need to try every possibility?

Examples.

```
SudokuSubsetsPermutationCombination SumMazeN Queens
```

↓

Backtracking Plugin.

---

BRO.

Notice.

We haven't chosen code.

We've chosen

thinking.

---

# Phase 2

# Where does information flow?

Ask.

```
Parent
↓
Child ?
```

↓

Parameter.



Or

```
Child
↓
Parent ?
```

↓

Return.

Need both?

↓

Hybrid.




Need neither?

↓

Traversal.





# Phase 3

# Where does the answer live?

This chapter we just built.

Question.

Does answer belong to...

---

Parent?

↓

Parameter.

---

Child?

↓

Return.

---

Whole tree?

↓

Global.

---

Journey?

↓

Shared State.

---

Done.

---

# Phase 4

# Which plugins do I install?

Now the fun begins.

Question.

Need what?

---

Visited?

↓

Traversal Plugin.

---

Running Sum?

↓

Entry Plugin.

---

Height?

↓

Exit Plugin.

---

Current Path?

↓

Push Plugin.

↓

Pop Plugin.

---

Gray State?

↓

Cycle Plugin.

---

Timer?

↓

Euler Plugin.

---

Finish Order?

↓

Topo Plugin.

---

Low Link?

↓

Bridge Plugin.

---

Notice.

I'm no longer thinking

algorithms.

Only plugins.




# Phase 5

# Build The Engine

The engine NEVER changes.
```
# Phase 5
dfs(node)
{
    //----------------
    // ENTER
    //----------------

    Entry Plugins

    for(each child)
    {
        dfs(child);
    }

    //----------------
    // EXIT
    //----------------

    Exit Plugins
}
```




```
                    TREE / GRAPH / STATE SPACE
                               │
                               ▼
                    What is the objective?
                               │
        ┌────────────┬─────────────┬─────────────┬─────────────┐
        ▼            ▼             ▼             ▼
   Explore      Parent Knows   Children Know   Try Choices
        │            │             │             │
 Traversal      Top Down      Bottom Up     Backtracking
        │            │             │             │
        └────────────┴─────────────┴─────────────┘
                               │
                               ▼
                Where does information live?
                               │
      Parameter   Return   Global   Shared State
                               │
                               ▼
                    Install Required Plugins
                               │
        visited | gray | timer | path | low | finish | ...
                               │
                               ▼
                      Plug into DFS Engine
                               │
                               ▼
                           Solve Problem
```







## Pattern 1

Traversal DFS

Problems

```
✓ Number of Islands✓ Max Area of Island✓ Provinces✓ Flood Fill✓ Reachability✓ Surrounded Regions
```

Recognition

Common mistakes

Template

Revision

---

## Pattern 2

Top Down

```
✓ Path Sum✓ Binary Tree Paths✓ Root to Leaf Sum✓ Prefix State
```

---

## Pattern 3

Bottom Up

This is HUGE.

```
✓ Height✓ Diameter✓ Balanced Tree✓ Maximum Path Sum✓ Subtree Sum✓ Subtree Size✓ Largest BST✓ Tree DP Introduction
```

---

## Pattern 4

Backtracking

```
✓ Subsets✓ Permutations✓ Combination Sum✓ N Queens✓ Sudoku✓ Rat in Maze
```

This is where muscle memory comes from.

---

# LEVEL 3 — Advanced DFS Bibles ❌

This is where most people say

> "Advanced Graph."

I don't want to teach them like that.

Each deserves its OWN Bible.

---

## Euler Tour Bible

Not

```
tintout
```

No.

Questions like

Why do timestamps exist?

Why does subtree become interval?

Why flatten tree?

---

## Cycle Detection Bible

Not

Gray.

Questions like

Why does Gray imply cycle?

Why not Black?

Why directed different?

---

## Topological Sort Bible

Not

Stack.

Questions like

Why finish order?

Why reverse?

Why DAG only?

Why Kahn also works?

---

## Low Link Bible

One of the hardest.

Questions.

```
Why low?Why bridge?Why articulation?Why back edge?
```

---

## SCC Bible

Kosaraju.

Tarjan.

Component graph.

Condensation graph.

---

## Tree DP Bible

This alone deserves

40 pages.

---

## LCA Bible

Euler

Sparse Table

Binary Lifting

RMQ

---

# LEVEL 4 — DFS Recognition Bible ❌

Exactly like BFS.

The final operating system.

Example.

```
Tree?↓Need subtree answer?↓Bottom Up.↓Need current path?↓Backtracking.↓Need parent info?↓Top Down.
```

This is the interview OS


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



```
WHITE

↓

ENTER

↓

GRAY

↓

ENTRY PLUGIN

↓

CHILD LOOP

↓

EXIT PLUGIN

↓

BLACK

↓

RETURN
```



```
Need DFS?

↓

What changes?

────────────────────────

Need only exploration?

↓

Traversal Plugin

────────────────────────

Need information from parent?

↓

Entry Plugin

↓

Top Down

────────────────────────

Need information from children?

↓

Exit Plugin

↓

Bottom Up

────────────────────────

Need temporary decisions?

↓

Entry = Apply

Exit = Undo

↓

Backtracking

────────────────────────

Need cycle detection?

↓

Gray-State Plugin

────────────────────────

Need ordering after completion?

↓

Exit-Time Plugin

↓

Topological Sort

────────────────────────

Need subtree intervals?

↓

Euler Tour Plugin

────────────────────────

Need bridge / articulation?

↓

Low-Link Plugin
```


