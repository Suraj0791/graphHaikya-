
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
