

We have discovered that every node has

```
Discovery Time
```

and

```
Finish Time.
```

A curious person would naturally ask:

> **Can these timestamps tell us something even deeper than ancestor relationships?**

Imagine removing one edge.

Can timestamps tell us whether that edge was the **only bridge** connecting two parts of the graph?

Or imagine removing one vertex.

Can timestamps reveal whether that vertex was **critical** for connectivity?

Those questions give birth to the next member of the DFS Time Family.




And here's something you'll appreciate after everything we've built:

**Low-Link will no longer feel like a brand-new algorithm.**

It is simply Euler Tour asking a deeper question:

> **"Now that every node has a discovery time... how far back in time can this subtree still reach?"**

That single question creates:

- Bridges
- Articulation Points
- Tarjan's algorithm
- Eventually SCC thinking

Exactly the same way Topological Sort was born naturally from DFS exit order.





Without deleting every edge one by one...

can DFS tell us

which edges are

**critical?**

---

Naive solution.

For every edge

```
Remove Edge↓Run DFS↓Still connected?
```

Complexity

```
O(E × (V+E))
```

Terrible.



# Euler Only Recorded

Remember.

Euler Tour stored

```
When did I arrive?
```

It never asked

```
Can I go back?
```

That's a completely different question.

---

# This Is The Missing Information

Euler knows

```
Arrival Time.
```

But connectivity is not about

arrival.

Connectivity is about

**escape.**



# Imagine Social Networks

Suppose

```
A joined first.B joined second.E joined third.F joined fourth.
```

Now ask F.

> What's the earliest member you can still message without leaving your connected group?

That answer tells us how "connected" F really is.

Not when F joined.

But how far back F's network reaches




> Euler already gave me **when I arrived**.

Now I need to know

> **How far back can I still reach?**

That naturally creates another array.

```
Discovery↓Reachability↓low[]
```

We haven't defined it yet.





Euler Tour tells us when a node entered history. Low-Link asks a deeper question: from this node's subtree, what is the earliest moment in DFS history that is still reachable? Low-Link is not about arrival—it is about the oldest reachable past.


### 1. The Physics of the "Escape Route"

In Euler Tour, we recorded time like a historian: _"Node F arrived at time 4."_ It is a historical log.

But connectivity (the core of Low-Link) isn't about history; it's about **possibility**. The question changes from "What happened?" to **"What can I still reach?"**

Think of your DFS search as a construction of a **hierarchy** (a tree of discovery).

- **The Tree Edges:** The paths you took to discover new nodes (e.g., $A \to B \to E$).
    
- **The Back Edges:** The hidden "shortcuts" that connect a node back to one of its own ancestors (e.g., $F \to B$).
    

**The Core Realization:**

If you are at node $F$ and you see an edge to $B$ (which is your ancestor), you have just found a **"hole in the wall"** of your subtree. You have found a path that allows you to "escape" back to an earlier part of the DFS history without using the edge that brought you here ($E \to F$).




### 2. The Mental Model: The "Escape Bubble"

Imagine each subtree in your DFS is inside a giant **waterproof bubble**.

- **In a standard tree:** Every bubble is completely isolated. You cannot escape a bubble to reach an ancestor without crossing the edge that connected you to it.
    
- **In a graph with cycles:** Some edges act as "straws" connecting the inside of your bubble to the outside world (an ancestor).



**Low-Link is simply the measurement of the "oldest" point you can reach through your bubble's straws.**

- `tin[u]` = When I arrived at the party.

- `low[u]` = What is the oldest person at the party I can still talk to, given my current position and all the shortcuts available to me?



Discovery

|Node|disc|
|---|---|
|A|1|
|B|2|
|C|3|
|D|4|



Suppose I'm standing at

```
D
```

What does

```
disc[D] = 4
```

actually tell me?

Answer:

> **The moment I first arrived at D.**

Nothing more.

Not where D can go.

Not who D can reach.

Only

```
Arrival Time
```




# Imagine Two Different Worlds

## World 1
no back edge 

World 2
Now D has a back edge to A.


Question.

What is

```
disc[D]
```

in both worlds?

Exactly the same.

```
4
```

Interesting.


### To answer your question about the "Back Edge":

In the context of **Bridges and Articulation Points** (which is what the Low-Link Bible is usually about), we are almost always talking about **Undirected Graphs**.

In an undirected graph, a **Back Edge** is:

> Any edge $(u, v)$ where $v$ is already visited, and $v$ is **NOT** the parent of $u$.

**That is it.** That is the "hole in the bubble" we talked about. If you are at $D$, and you see an edge to $A$, and $A$ is not your parent, $A$ is an ancestor. You just found a path that allows you to bypass the edge $(C, D)$. That edge $(C, D)$ is now **proven** not to be a bridge.






# Think Like A Tourist

Suppose four cities.

```
DelhiMumbaiGoaKerala
```

You visited them in order.

```
Delhi = Day 1 Mumbai = Day 2 Goa = Day 3    Kerala = Day 4
```

Question.

Does

```
Kerala = Day 4
```

tell us

whether flights exist back to Delhi?

No.

It only tells us

when you first arrived.

Exactly the same.

---

# We Need Another Number

Standing at D...

I don't just care

```
When did I arrive?
```

I care

```
How old a node can I still reach?
```

Notice.

That's an entirely different property.




Completely changed.

Discovery records

History.

Low records

Escape ability.


# The Cave Analogy

Imagine caves.

Question.

Standing at D...

Can you escape back to Entrance?

Without retracing your parent edge?

If yes...

Then

```
low
```

becomes very small.

If no...

You're trapped.

Then

```
low=disc
```

# Why "Minimum"?

Notice the wording.

We always ask

```
EarliestOldestSmallest Discovery Time
```

Why?

Because older means

closer to DFS root.

The earliest ancestor is the hardest one to reach.

If you can reach that...

you can obviously reach everyone below it.

So only the minimum matters.




> **`disc[u]` tells us when `u` entered DFS history. `low[u]` tells us how far back in DFS history `u`'s entire subtree can still reach. Discovery is personal; low is collective.**


# 📖 LOW-LINK BIBLE

# Chapter 2 — Information Flows Upward

---

> **This is the chapter where `low[]` stops looking magical.**

## DFS Core Bible

We asked:

> **How does a parent know the height of its subtree?**

Answer?

Children compute it first.

Then return it upward.





# Imagine DFS Is Real People

Suppose

D discovers a secret tunnel.

```
Tunnel↓A
```

Does B know?

No.

B is still waiting.

It has not finished.

---

Who knows?

Only D.

---

When D finishes...

it returns to C.

Question.

Should D keep the secret?

Or tell C?

Obviously tell C.

---

Now C knows.

When C finishes...

it tells B.

Then

B tells A.

Exactly.

Information climbs upward.

---

# This Is Backtracking Again

Remember what we learned months ago?

Backtracking is not just

```
Going Back.
```

It is

```
Returning Information.
```

Low-Link is another application of exactly that principle.

Nothing new.

---


Every node starts by assuming

> "The oldest node I can reach is myself."

That's the default belief.





.

# 📖 LOW-LINK BIBLE: The Information Flow

## 1. The Core Mystery: How Does Information Climb?

In the graph $A \to B \to C \to D$ with back edge $D \to A$, **only $D$ discovers the edge.** $B$ and $C$ never see it. Yet, by the end, $B$ knows its `low` value is $1$.

**The Answer:** DFS backtracking is not just "going back." It is a **recursive summary.**

- **Going Down:** We discover nodes and assign `disc[]`.
    
- **Coming Back:** We pass knowledge up the chain.
    

## 2. The Movie: Step-by-Step Dry Run

Tree: $A \to B \to C \to D$ | Back Edge: $D \to A$ | Discovery: $A=1, B=2, C=3, D=4$

1. **DFS reaches $D$:**
    
    - `low[D]` starts at `disc[D]` ($4$). Default belief: "The oldest node I can reach is myself."
        
    - **$D$ sees back edge to $A$:** $D$ updates `low[D] = min(4, disc[A]) = 1$.
        
2. **$D$ returns to $C$:**
    
    - $D$ tells $C$: "My subtree reached discovery time $1$."
        
    - $C$ updates: `low[C] = min(low[C], low[D]) = min(3, 1) = 1$.
        
3. **$C$ returns to $B$:**
    
    - $C$ tells $B$: "My subtree reached $1$."
        
    - $B$ updates: `low[B] = min(2, 1) = 1$.
        
4. **$B$ returns to $A$:**
    
    - Information has climbed to the top. Everyone knows.
        

## 3. The Physics of the Belief System

- **Default Belief (Entry):** `low[u] = disc[u]`.
    
- **Recursive Summary (Exit):** `low[u] = min(low[u], low[v])` (inherit child's findings).
    

## 4. Why This Unifies Everything

You already know this physics. It is a **Bottom-Up DFS**.

|**Algorithm**|**Child Tells Parent**|**Parent Action**|
|---|---|---|
|**Height**|"My subtree height is $H$"|Inherit/Add 1|
|**Diameter**|"My longest branch is $L$"|Inherit/Update Global|
|**Low-Link**|"My subtree reached time $T$"|Inherit min($T$)|

## 🧠 The Bible Sentence

Discovery times are fixed while DFS goes down (History); Low values are negotiated while DFS comes back up (Reachability). Every parent simply adopts the oldest reachability claim made by its children.


```
// Inside DFS(u)
low[u] = disc[u]; // Default: I only know myself

for (int v : adj[u]) {
    if (v == parent) continue; 
    if (visited[v]) {
        // BACK EDGE: Found a shortcut!
        low[u] = min(low[u], disc[v]); 
    } else {
        dfs(v, u); 
        // BACKTRACKING: Inherit child's findings
        low[u] = min(low[u], low[v]); 
    }
}
```

