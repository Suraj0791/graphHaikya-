



### The 3 Things DFS Sees (The "Physical Rules")

When you are exploring a graph with DFS, you are coloring nodes as you go:

- **WHITE:** Never seen.
- **GRAY:** Currently on your path (in the stack).
- **BLACK:** Finished (we explored everything reachable from here).

#### 1. The "Back Edge" (The Cycle Detector)

When you are at node $u$ and you see a neighbor $v$:

- If $v$ is **GRAY**, it means you just bumped into your own ancestor. You have found a **Cycle**.
- **Why this matters:** A cycle is a "loop." If you have a loop, it means there are at least two paths to get somewhere. **If there are two paths, you cannot have a Bridge or an Articulation Point.**
- **The Math:** This is where `low[u] = min(low[u], disc[v])` comes from. You are saying, "I have a shortcut back to my ancestor."

#### 2. The "Bridge" / "Articulation Point" (The Vital Link)

After you return from exploring a child $v$, you ask: "Could $v$ get back to me (or higher) without using the road $(u, v)$?"

- If `low[v] > disc[u]`, the answer is **NO**.
- **The Physical Reality:** You are the only person holding up that subtree. If you cut the edge $(u, v)$, the entire subtree $v$ falls into the abyss.
- **Why this matters:** This is the definition of a **Bridge**.

#### 3. The "SCC" (The Strongest Connection)

If the graph is **Directed**, cycles are special. In a directed graph, if $A$ can reach $B$ AND $B$ can reach $A$, they are in a "Strongly Connected Component" (SCC).

- **The Physics:** An SCC is just a collection of nodes where everyone can reach everyone.
- **The Engine:** Tarjan’s algorithm (or Kosaraju’s) is just a way to keep track of who is currently in a "cycle bubble." When the DFS finishes for a subtree and it realizes it can't escape to an older node (because it’s trapped in a cycle), it "pops" that bubble as an SCC.

### Why you are confused (The "Terms" Trap)

|**The "Scary" Term**|**What it actually means**|
|---|---|
|**Back Edge**|A physical loop where you see an ancestor.|
|**Low-Link**|A value representing the "highest" (oldest) ancestor you can reach.|
|**SCC**|A cluster of nodes where you can travel in a circle forever.|
|**Bridge**|An edge that, if deleted, disconnects the graph (no "shortcuts" exist).|

### The "One Engine" Framework

You don't need to learn these separately. You just need to change the **Exit Plugin** of your DFS engine:

1. **If you want Bridges:**
    - **Plugin:** `if (low[v] > disc[u])` $\rightarrow$ "This edge is a bridge."
2. **If you want SCCs (Tarjan's):**
    
    - **Plugin:** Keep a stack of nodes. When `low[u] == disc[u]`, you have found the "root" of an SCC. Pop everything off the stack until you hit $u$. That pile of nodes is your SCC.


### Do this for your mental sanity:

Stop looking at the algorithms. Look at the **problem**:

- **Undirected Graph + Want to know if it splits?** $\rightarrow$ You are looking for **Bridges**. Use the `low[]` logic.
- **Directed Graph + Want to know who can reach who?** $\rightarrow$ You are looking for **SCCs**. Use the Tarjan/Stack logic.


**Does this distinction help?** You aren't learning 3 different things; you are learning **one DFS engine** that just looks for different "physical signals" (shortcuts vs. cycles) in the graph.



# Euler asked

> **When did I enter?**

↓

Got

```
tintout
```

# Low-Link asked

> **How far back can I still reach?**

↓

Got

```
low
```



Who belongs together?

Not

parents.

Not

subtrees.

Instead

> **Which nodes form one world where everyone can reach everyone else?**

That's an entirely new mystery.





# The New Physics

Euler introduced

```
TIME
```

Low-Link introduced

```
ESCAPE
```

SCC introduces

```
MUTUAL REACHABILITY
```



# Let's Go Back

Remember the very first graph problems we solved?

```
A —— B —— C

D —— E
```

Question.

How many connected components?

Easy.

```
{A,B,C}{D,E}
```

Done.

Life was simple.




# Why Was It So Simple?

Because edges had a magical property.

```
A —— B
```

Question.

Can A reach B?

Yes.

Can B reach A?

Also yes.

Interesting.

Every road worked

both ways.



# The Hidden Law

Undirected graphs secretly obey

```
Reachability=Mutual Reachability
```

If I can reach you...

you can reach me.

Direction doesn't exist.



Replace

```
A —— B
```

with

```
A → B
```

Question.

Can A reach B?

Yes.

Can B reach A?

...

No.

Everything changed.

One tiny arrow.

Entire universe changed.




A → B → C


Can C reach A?
No.
Interesting.
The graph is connected...but also
not connected.
Wait.
What?



# The First Confusion

Suppose someone asks

> "Are A and C connected?"

What's the answer?

If they mean

```
Can A reach C?
```

Answer

Yes.

If they mean

```
Can C reach A?
```

Answer

No.

The word

```
Connected
```

has become ambiguous.




# Ordinary Connected Components Break

Imagine this graph.

```
A → B → C
```

Question.

How many connected components?

Old thinking says

```
1
```

Because everything touches.

But...

Can everyone reach everyone?

No.

Something is wrong.



# The New Physical Law

Undirected graphs cared about

```
Reachability.
```

Directed graphs care about

```
Mutual Reachability.
```

This is the biggest conceptual shift.

