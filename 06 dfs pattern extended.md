

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


