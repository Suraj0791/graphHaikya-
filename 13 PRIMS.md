KRUSKAL IS EDGE CENTRIC 



## Engineer 2 (Prim)

He looks at Kruskal and says

> Why are you sorting every road?

> I don't care about roads.

> I care about **growing one connected network.**





# MST Universe

We already know one engineer.

## Engineer 1 (Kruskal)

He walks into the room and says:

> "Forget the graph."

> "Show me every road."


Road A-B   ₹2

Road C-D   ₹1

Road B-C   ₹5

Road A-D   ₹4



He immediately says

> Sort them.

Then

```
Cheapest
↓
Cycle?
↓
No
↓
Take it
```






The tree keeps expanding.

Exactly like BFS.

But...

instead of

> **nearest vertex**

Prim chooses

> **cheapest outgoing edge.**

Huge difference.




Kruskal thinks

Entire graph

↓

Sort ALL edges

↓

Build many small trees

↓

Merge them




He starts with

```
A    B    C    D
```

Everything disconnected.

Then slowly merges components




Prim thinks

Start ONE tree

↓

Grow it

↓

Grow it

↓

Grow it



He starts with

```
A
```

and keeps expanding.


# This is the deepest difference.

## Kruskal

Starts with

```
N trees
```


Ends with

```
One tree
```



## Prim

Starts with

```
One tiny tree
```

```
A
```

Ends with

```
One big tree
```



This one picture explains everything.
```
KRUSKAL

A   B   C   D

↓

Merge

↓

Merge

↓

Merge

↓

One Tree




PRIM

A

↓

A-B

↓

A-B-C

↓

A-B-C-D


```


# Why doesn't Prim need DSU?

Think carefully.

Can Prim create two separate trees?

No.

He always grows

**one existing tree**.

There is never a question like

```
Same component?
```

because there is only one growing component.

That's why DSU disappears completely.





# The Priority Queue Engine

> We know the proof.

Now we need a machine that repeatedly answers:

> **"What's the cheapest edge leaving my current tree?"**





# Compare with Dijkstra

This is where many students get confused.

Let's compare them.

|Prim|Dijkstra|
|---|---|
|Goal: Build MST|Goal: Shortest paths|
|Priority = Edge weight|Priority = Total distance from source|
|Add cheapest edge leaving tree|Add vertex with smallest known distance|
|No relaxation|Relaxation is the core|
|visited[] means "already in MST"|visited[] means "shortest distance finalized"|




The **code skeleton** looks similar because both use:

- Min Priority Queue
- visited[]
- Graph adjacency list

But the **meaning** is completely different.

This distinction is crucial.





# Why no relaxation?

Imagine

```
A → B = 5A → C = 2C → B = 3
```

In Dijkstra, you'd ask:

> Can I improve B's shortest distance through C?

That's relaxation.

Prim doesn't care about path lengths at all.

It only asks:

> What's the cheapest edge that brings a **new vertex** into my tree?

No distance arrays.

No path optimization.

Just edge selection.

```
Start with any vertex
        │
        ▼
Mark visited
        │
        ▼
Push all outgoing edges into PQ
        │
        ▼
Pop cheapest edge
        │
   ┌────┴────┐
   │         │
Destination  Already
visited?     outside?
   │             │
 Skip         Add edge to MST
                 │
          Mark new vertex visited
                 │
          Push its outgoing edges
                 │
                Repeat
```





# Step 0

Pick any vertex.

This surprises many beginners.

**It literally doesn't matter.**

Let's start at



Push every outgoing edge.

PQ



# Step 1

Pop minimum.

PQ gives


Now something important happens.

A new vertex joined.

So we discover new roads.

Push

push in pq




# The Invariant

At every moment during Prim:

```
Selected edges        
│
▼
Always form ONE connected tree
```

Never a forest.

Never a cycle.

Always one growing tree.

This is Prim's most important invariant

```
Choose any start
        │
        ▼
Current Tree
        │
        ▼
Push all outgoing edges
        │
        ▼
Priority Queue chooses cheapest
        │
   ┌────┴────┐
   │         │
Visited?    New vertex?
   │            │
 Skip        Add edge
                │
        Expand the tree
                │
      Push new outgoing edges
                │
             Repeat
```


```
pq.push({0,0});

while(!pq.empty()){

    auto [wt,node]=pq.top();

    pq.pop();

    if(vis[node])
        continue;

    vis[node]=true;

    mstCost+=wt;

    for(auto [next,w]:adj[node]){

        if(!vis[next]){

            pq.push({w,next});

        }
    }
}
```







# Complexity

Each edge may enter the PQ.

```
E pushes
```

Each push/pop

```
log V
```

Total

```
O(E log V)
```




# Compare

Kruskal

```
Sort all edges↓O(E log E)
```

---

Prim

```
Priority Queue↓O(E log V)
```

Both are excellent.




Sparse Graph

```
Few edges
```

Kruskal

↓

Fantastic.

Sorting isn't expensive.

---

Dense Graph

```
Almost every pair connected
```

Prim often performs better because it avoids sorting the complete edge list and grows the tree incrementally. In practice, the exact performance also depends on the data structures used (binary heap, Fibonacci heap, adjacency matrix, etc.), but for interviews this intuition is enough.




# Prim vs Dijkstra

This is probably the most important comparison.

|Feature|Prim|Dijkstra|
|---|---|---|
|Goal|Minimum Spanning Tree|Shortest Paths|
|Priority Queue Key|Edge weight|Total distance|
|State|`(edgeWeight, vertex)`|`(distance, vertex)`|
|Relaxation|❌ No|✅ Yes|
|Output|One MST|Distance to every vertex|
|Greedy Choice|Cheapest edge leaving tree|Closest vertex from source|

The code skeleton is about **80% identical**.

The **thinking** is completely different.


