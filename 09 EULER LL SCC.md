

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

