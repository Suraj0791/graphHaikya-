
# 🔱 TC & SC OF GRAPHS (THE BRAHMASTRA)
Yeh woh Brahmastra hai jisse Graph ke kisi bhi question ki complexity interview mein 10 second mein nikal aayegi. Bina rate hue, poore intuition aur "WHY" ke sath todte hain isko.

---

## 💾 THE SPACE COMPLEXITY (SC) BRAHMASTRA
Ek simple universal formula dimaag mein baitha lo:
**Total Space = (Graph ko Store karne ka Space) + (Traversal Tools ka Space)**

### 1. Graph Storage Space (Data ko memory mein rakha kahan?)
* **Adjacency Matrix:** Space = **`O(N^2)`**
  * *Why?* Kyunki hum poora `N x N` ka dabba banate hain. Agar 100 node hain, toh 10,000 cells banenge, bhale hi unme sirf 2 edges hon. Baaki sab `0` padhe rahenge, space waste!
* **Adjacency List:** Space = **`O(N + E)`**
  * *Why?* Yahan multiplication nahi, addition ho raha hai. Tumne `N` size ka vector banaya (Space: `N`). Us vector ke andar choti-choti lists hain. Agar saari choti lists ke items ginoge, toh wo total Graph ke edges `E` ke barabar honge (Space: `E`). Total physically consumed memory: **`N + E`**.
* **Grid (Implicit Graph):** Space = **`O(1)`** Extra Space.
  * *Why?* Grid pehle se array (input) mein diya hota hai. Hum alag se koi `matrix` ya `list` create nahi karte. Jo input mila, usi pe algorithm chala diya.

### 2. Traversal Tools Space (Code chalane ke liye kya use kiya?)
* **Visited Array:** Space = **`O(N)`**
  * *Why?* Har node par mark lagane ke liye ek array toh chahiye hi, nahi toh loop mein phas jayenge.
* **DFS Recursion Stack / BFS Queue:** Worst-case Space = **`O(N)`**
  * *Why N?* Imagine ek straight-line graph hai (`1 -> 2 -> 3 -> 4`). DFS chalayenge toh ek ke baad ek function call hota jayega, aur memory mein ek sath `N` functions khade ho jayenge stack ke roop mein. BFS mein queue mein max elements jayenge.

**🏆 FINAL SC VERDICT:**
* Standard Graph (using Adj List): `O(N + E) [Graph] + O(N) [Tools] =` **`O(N + E)`**
* Grid Questions: `O(1) [Graph] + O(R*C) [Tools] =` **`O(R * C)`**

---

## ⏱️ THE TIME COMPLEXITY (TC) BRAHMASTRA
Sabse bada trap (jahan maximum log phas jate hain): *"Arre! DFS mein node par jate hain aur fir node ke andar `for` loop lagate hain. Toh loop ke andar loop matlab `O(N * E)` hua na?"* **BILKUL GALAT.**

Time Complexity = (Nodes ko visit karne ka time) + (Edges ko check karne ka time).

### The "Why N + E" Breakdown (The Postman Intuition):
Aaja code ko open karke chalate hain:
```cpp
void dfs(int node) {
    vis[node] = 1; // Step A: Node visit kiya
    for (int neigh : adj[node]) { // Step B: Uske neighbors (edges) check kiye
        if (!vis[neigh]) dfs(neigh);
    }
}
```



1. **Nodes ko visit karna (`O(N)`):** Kyunki hum `visited` array maintain karte hain, hum ek node par exactly **EK BAAR** hi jaate hain (Step A). Toh poore program ki execution mein, har node 1 baar visit hoga. Total steps for nodes = **`N`**.
2. **Edges par loop lagana (`O(E)`):** Jab tum ek node pe ho, tum `for` loop (Step B) us graph ki saari `E` edges par nahi chalate! Tum sirf us akele node ki apni edges par loop chalate ho. Agar graph mein 5 node hain, ho sakta hai Node 0 pe loop 2 baar chale, Node 1 pe 1 baar, aur Node 2 pe 0 baar. Agar poore recursion cycle ke baad tum ginoge ki ye andar wala `for` loop _total mila kar_ kitni baar chala, toh exact answer aayega total number of edges ke barabar! Total loop checks = **`E`** (ya `2E` in undirected).

_Time = N baar node par gaye **+** Total mila kar E baar loop chala =_ **`O(N + E)`**

**🏆 FINAL TC VERDICT:**

- Standard Graph (DFS/BFS): **`O(N + E)`**
- Grid Questions: Total nodes hain `R*C`. Ek cell ke max 4 neighbors hain. TC = `O(R*C [Nodes] + 4*(R*C) [Edges])`. Constant `4` ko hataya toh TC = **`O(R * C)`**.











# Step 1: Always identify

- **V** = Number of Vertices (nodes)
- **E** = Number of Edges

Everything is built from these two.

---

# DFS / BFS

### Mental picture

Every node is visited **once**.

Every edge is explored **once** (undirected: effectively twice in adjacency lists, but still **O(E)**).

So

```
Time = O(V + E)
```

### Easy memory

> **Visit Nodes + Traverse Edges**

```
O(V + E)
```

---

### Space

Visited array

```
O(V)
```

DFS recursion stack / BFS queue

Worst case

```
O(V)
```

Total

```
O(V)
```

---

# Dijkstra (Priority Queue)

Think

```
Normal BFS

+

Priority Queue
```

BFS

```
O(V+E)
```

Priority Queue operations

Every edge can cause a push.

Each push/pop

```
log V
```

Therefore

```
O((V+E)logV)
```

Usually written as

```
O(E log V)
```

because

```
E ≥ V-1
```

for connected graphs.

---

Space

```
visited

dist

priority queue

=
O(V)
```

(PQ can temporarily hold more entries because of duplicate relaxations, but for interviews you typically state `O(V)` auxiliary plus graph storage. If discussing the priority queue itself in detail, it can grow to `O(E)` entries.)

---

# Bellman Ford

Relax

```
E edges
```

Repeat

```
V-1 times
```

So

```
O(VE)
```

---

# Floyd Warshall

Three nested loops

```
k
 i
  j
```

So

```
O(V³)
```

Space

```
O(V²)
```

---

# Topological Sort

DFS

```
O(V+E)
```

Kahn's BFS

```
O(V+E)
```

---

# Cycle Detection

DFS

```
O(V+E)
```

BFS (Kahn)

```
O(V+E)
```

---

# DSU

One operation

```
≈ O(1)
```

Actually

```
O(α(N))
```

where `α` (inverse Ackermann) grows so slowly that it's treated as constant.

If processing

```
E edges
```

Total

```
O(E α(V))
≈ O(E)
```

---

# MST

## Kruskal

Sort edges

```
O(E log E)
```

DSU

```
O(E)
```

Total

```
O(E log E)
```

---

## Prim

Priority Queue

```
O(E log V)
```

---

# 0-1 BFS

Deque operations

```
O(1)
```

Every edge once

```
O(V+E)
```

---

# SCC (Kosaraju)

Two DFS

```
2 × O(V+E)
```

Still

```
O(V+E)
```

---

# Tarjan (SCC / Bridges / Articulation)

One DFS

```
O(V+E)
```

---

# Interview Trick (95% of graph problems)

Ask yourself:

### Am I traversing each node once?

Yes

↓

### Am I traversing each edge once?

Yes

↓

**Time = `O(V + E)`**

---

### Is there a Priority Queue?

Yes

↓

Multiply by

```
log V
```

---

### Am I sorting edges?

Yes

↓

Add

```
E log E
```

---

### Am I relaxing every edge V−1 times?

Yes

↓

```
VE
```

---

### Three nested loops over vertices?

Yes

↓

```
V³
```

---

# The Cheat Sheet

|Algorithm|Time|Space|Memory Trick|
|---|---|---|---|
|DFS|`O(V+E)`|`O(V)`|Visit every node & edge once|
|BFS|`O(V+E)`|`O(V)`|Same as DFS|
|Topo DFS|`O(V+E)`|`O(V)`|DFS|
|Kahn|`O(V+E)`|`O(V)`|BFS|
|Cycle Detection|`O(V+E)`|`O(V)`|DFS/BFS|
|Dijkstra|`O(E log V)`|`O(V)`*|DFS/BFS + Priority Queue|
|0-1 BFS|`O(V+E)`|`O(V)`|BFS + Deque|
|Bellman-Ford|`O(VE)`|`O(V)`|Relax all edges `V-1` times|
|Floyd-Warshall|`O(V³)`|`O(V²)`|3 nested loops|
|Kruskal|`O(E log E)`|`O(V)`|Sort edges + DSU|
|Prim|`O(E log V)`|`O(V)`*|Dijkstra for MST|
|Kosaraju|`O(V+E)`|`O(V)`|Two DFS|
|Tarjan|`O(V+E)`|`O(V)`|One DFS|

*The auxiliary arrays are `O(V)`. If you account for duplicate entries in the priority queue, its size can reach `O(E)` in the common implementation without decrease-key.

## One-line interview heuristic

> **Traverse once → `O(V+E)`**  
> **Add a Priority Queue → `× log V`**  
> **Sort edges → `E log E`**  
> **Repeat over all vertices → `VE`**  
> **Triple nested vertex loops → `V³`**



