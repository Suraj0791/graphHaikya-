

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


