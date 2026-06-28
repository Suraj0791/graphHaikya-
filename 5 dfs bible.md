
```
GRAPHS

│
├───────────────
│ FOUNDATION
├───────────────

Graph Physics

↓

BFS Bible ✅

↓

BFS Pattern Book (your question list)

↓

DFS Core Bible ✅

↓

DFS Pattern Book   ← NEXT

↓

Cycle Detection Bible

↓

Topological Sort Bible

↓

Euler Tour Bible

↓

Low-Link Bible

↓

SCC Bible

↓

Tree DP Bible

↓

LCA Bible

↓

Dijkstra Bible

↓

Dijkstra Pattern Book

↓

Bellman-Ford Bible

↓

Floyd-Warshall Bible

↓

Johnson Bible

↓

DSU Bible

↓

DSU Pattern Book

↓

Kruskal Bible

↓

Prim Bible

↓

Graph Operating System

END
```



# FIRST PRINCIPLE

DFS is **not an algorithm.**

DFS is a behavior.

The behavior is

> "Whenever I choose a path,  
> I keep following that path  
> until I absolutely cannot continue."

That's it.

Everything else comes later.



DFS has one soul sentence:

> **"Finish one path completely before giving attention to another."**

Everything in DFS comes from this.

Not recursion.
Not stack.
Not trees.
Not graphs.



People say
> "DFS uses recursion.

Wrong.

People say

> "DFS uses a stack."
Still backwards.



The truth is

> **DFS creates a problem.**
> **The stack is simply the only thing that can solve that problem.**

Exactly like BFS.
Nobody invented the queue first and then BFS.
The exploration strategy demanded a queue.


DFS is

**the exploration strategy.**
Recursion is
**one implementation.**
Stack is
**the mechanism.**
Three completely different things.



# Mental Models You Should Carry Forever

1. **Breadcrumbs in a cave** — every step in, drop one; every step out, pick up the latest.
2. **Nested folders** — finish the deepest folder before returning.
3. **Browser Back button** — you always return to the most recently opened page.
4. **Promises** — the stack stores unfinished promises, not completed history.
5. **Paused work** — a stack frame is a frozen snapshot of what remains to be done.


### Family 1

Traversal

```
Number of IslandsFlood FillProvincesMax AreaSurrounded RegionsKeys & RoomsConnected Components
```

---

### Family 2

Top Down

```
DepthPath SumBinary Tree PathsRoot to Leaf Numbers...
```

---

### Family 3

Bottom Up

```
HeightBalancedDiameterMax Path SumSubtree SumLargest BSTHouse Robber III
```

---

### Family 4

Backtracking

```
SubsetsPermutationsCombination SumSudokuN Queens...
```

This is **one Pattern Book**.

Not four Bibles.



# After the Pattern Book?

NOW...

we meet NEW concepts.

These deserve Bibles because we haven't explained WHY yet.

For example...

---

## Cycle Detection Bible

Question:

> Why does Gray detect cycles?

That's a mystery.

Needs a Bible.

---

## Topological Sort Bible

Question:

> Why does Exit Order become dependency order?

Mystery.

Needs a Bible.

---

## Euler Tour Bible

Question:

> Why does a subtree become one interval?

Mystery.

Needs a Bible.

---

## Low-Link Bible

Question:

> Why does one integer detect bridges?

Huge mystery.

Needs a Bible.

---

## SCC Bible

Question:

> Why do two passes magically find SCCs?

Needs a Bible.

---

## Tree DP Bible

Question:

> Why does returning a state solve optimization?

Needs a Bible.

---

## LCA Bible

Question:

> Why does binary lifting answer ancestors in log N?

Needs a Bible.



