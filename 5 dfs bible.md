
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


```
             ENTER

               │

               ▼

        Do Entry Work

               │

               ▼

      More Children?

        /          \

      YES          NO

      │             │

      ▼             ▼

Go to Child       EXIT

      │             │

      └────Resume───┘

               │

               ▼

        Do Exit Work

               │

               ▼

            Return
            
            
```




This...

is DFS.

Not recursion.

Not stack.

**This engine.**

---

# Question

Where can algorithms differ?

Can they change

```
ENTER?
```

No.

Every DFS enters.

Can they remove

```
Child Loop?
```

Impossible.

Can they remove

```
EXIT?
```

Impossible.

So...

What actually changes?

Only the work.

---

# Plugin System

Exactly like BFS.

---

## Traversal Plugin

Entry

```
visited = true
```

Exit

```
Nothing
```

---

## Top Down Plugin

Entry

```
Pass information
```

Exit

```
Nothing
```

---

## Bottom Up Plugin

Entry

```
Nothing
```

Exit

```
Combine child answers
```

---

## Backtracking Plugin

Entry

```
Modify state
```

Exit

```
Undo state
```

---

BROOOOO.

Now read this.

```
DFS Engine+Entry Plugin+Exit Plugin
```

Exactly.

Exactly like BFS.

---

# Another Huge Discovery

Question.

Where does every famous DFS problem differ?

Let's see.

---

### Height

Engine

Same.

Only Exit Plugin.

```
return 1+max(left,right)
```

---

### Diameter

Engine

Same.

Exit Plugin

changes.

---

### Balanced Tree

Engine

Same.

Exit Plugin

changes.

---

### Path Sum

Engine

Same.

Entry Plugin

changes.

---

### Flood Fill

Engine

Same.

Entry Plugin

changes.

---

### Subsets

Engine

Same.

Entry Plugin

```
Push
```

Exit Plugin

```
Pop
```

---

Do you see it?

Nothing changed.

---

# There Is Only One DFS

I'm going to say something bold.

There are not

```
Traversal DFSTop Down DFSBottom Up DFSBacktracking DFS
```

These are NOT different DFS algorithms.

There is only

```
DFS Engine
```

with different plugins.

Exactly how React has

```
React Engine+Components.
```

---

# The DFS State Machine

Now let's merge EVERYTHING.

Remember Gray.

Remember Entry.

Remember Exit.

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
dfs(node)
{
    //-----------------
    // ENTER
    //-----------------

    EntryPlugin();

    for(each child)
    {
        if(canVisit)
            dfs(child);
    }

    //-----------------
    // EXIT
    //-----------------

    ExitPlugin();
}
```



Nothing changes.

Ever.

Only these two boxes.

```
EntryPlugin()
ExitPlugin()
```

```
                    DFS ENGINE

          ENTER

             │

      Entry Plugin

             │

      Explore Children

             │

      Exit Plugin

             │

           RETURN

                │

      Plugin decides meaning

──────────────────────────────────

Traversal

↓

visited

──────────────────────────────────

Top Down

↓

Pass information

──────────────────────────────────

Bottom Up

↓

Return information

──────────────────────────────────

Backtracking

↓

Undo information

──────────────────────────────────

Cycle Detection

↓

Gray plugin

──────────────────────────────────

Topo

↓

Finish-order plugin

──────────────────────────────────

Euler Tour

↓

Time plugin

──────────────────────────────────

Bridges

↓

Low-link plugin
```




# DFS BIBLE

# The Immutable Engine

## (What NEVER Changes?)

---

Forget algorithms.

Forget problems.

Forget LeetCode.

I have a question.

Suppose I give you these problems.

```
Height

Diameter

Subtree Sum

Topological Sort

Connected Components

Sudoku

Permutations

Euler Tour

Bridges

LCA

Flood Fill

Path Sum

Maximum Path Sum
```



Question.

How many DFS algorithms are there?

Most people say

```
12
```

No.

There is exactly

```
1
```

One.

Let's prove it.



*


DFS has the same thing.

```
ENTER
↓
CHILD
↓
EXIT
```

Nothing else.


```
            ENTER
               │
               ▼
      Entry Plugin Runs
               │
               ▼
     Unexplored Child Exists?
          /             \
        YES             NO
         │               │
         ▼               ▼
    dfs(child)      Exit Plugin
         │               │
         └────Resume─────┘
               │
               ▼
             RETURN
```




# Now Let's Break Famous Problems

## Height

Where does logic happen?

Engine

```
ENTER↓CHILD↓EXIT
```

Plugin

```
EXITreturn 1 + max(...)
```

---

## Traversal

Engine

Same.

Plugin

```
ENTRYvisited = true
```

---

## Path Sum

Engine

Same.

Plugin

```
ENTRYrunningSum += node
```

---

## Euler Tour

Engine

Same.

Plugin

```
ENTRYtin[node]=timer++EXITtout[node]=timer++
```

---

## Topological Sort

Engine

Same.

Plugin

```
EXITanswer.push(node)
```

---

## Backtracking

Engine

Same.

Plugin

```
ENTRYpush()EXITpop()
```

---

Notice.

The engine never changed.

Not once.

---

# BRO.

Now something beautiful happens.

Suppose tomorrow I teach

Tarjan.

People think

```
New Algorithm
```

Wrong.

We'll ask

Question.

Where does Tarjan change the engine?

Does it change

Enter?

No.

Does it change recursion?

No.

Does it change child loop?

No.

Only plugin.

Exactly.

---

# We Can Compress DFS

Instead of remembering

```
TraversalTop DownBottom UpBacktrackingEulerTopoTarjanTree DP...
```

Your brain should remember

```
DFS ENGINE
```

Everything else becomes

```
Plugin Package
```

---

# Let's Build the Plugin Table

This is the table I wish every DSA book had.

|Plugin|Entry|Exit|Purpose|
|---|---|---|---|
|Traversal|Mark visited|Nothing|Consume one world|
|Top-Down|Update/pass state|Nothing|Carry information downward|
|Bottom-Up|Nothing|Combine & return|Gather information upward|
|Backtracking|Apply choice|Undo choice|Explore alternate universes|
|Euler Tour|Record entry time|Record exit time|Flatten recursive structure|
|Topological Sort|Nothing|Push node|Order by completion|
|Cycle Detection|Mark Gray|Mark Black|Detect back edges|
|Low-Link|Initialize discovery|Update low value|Bridges / articulation|

Don't memorize algorithms.

Memorize plugins.




# Wait...

Can Plugins Combine?

This is where advanced DFS is born.

Suppose I ask:

> Find all root-to-leaf paths.

Do we need just one plugin?

No.

Let's think.

Need current path.

That's

```
Backtracking Plugin
```

Need current sum.

That's

```
Top-Down Plugin
```

Need to save answer at leaves.

That's

```
Leaf Plugin
```

Suddenly.

One problem can install

multiple plugins.

Exactly like software.

---

# Example

Binary Tree Paths.

Engine

Same.

Plugins

```
ENTRY

push(node)

↓

Leaf

store answer

↓

EXIT

pop()
```

Three plugins.

One engine.





# The Plugin Design Algorithm

This is how I want you to think in interviews.

Instead of asking

> "Which algorithm?"

Ask:

### Step 1

What's the engine?

```
DFS
```

Fixed.

---

### Step 2

What should happen on Entry?

Maybe nothing.

Maybe `visited=true`.

Maybe `path.push_back()`.

Maybe `depth++`.

---

### Step 3

What should happen on Exit?

Maybe nothing.

Maybe `return height`.

Maybe `path.pop_back()`.

Maybe `answer.push_back(node)`.

---

### Step 4

Any extra state?

Gray?

Timer?

Low?

Parent?

Running sum?

That's it.

The whole solution is now designed


```
Engine

↓

Entry Plugins

↓

Exit Plugins

↓

Extra State



```





> **DFS is an execution engine that repeatedly performs three immutable actions: Enter a node, recursively delegate unfinished work to its children, and Exit after all delegated work is complete. Every DFS algorithm is created by attaching behavior to Entry, Exit, or maintaining additional state during this engine.**


