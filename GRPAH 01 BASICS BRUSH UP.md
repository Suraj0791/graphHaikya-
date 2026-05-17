
# 🚀 GRAPH REPRESENTATION (THE BEGINNING)

## 🤔 Kaha se shuruwat karein?
BFS, DFS, Cycle Detection, Topo Sort, Kahn's Algo... yeh sab baad ki baatein hain.  
Sabse pehle aur sabse zaroori cheez: **Graph kaam kaise karta hai aur code mein isko represent kaise karte hain?**

---

## 📖 KAHANI SHURU: GURU GRAPH KAISE REPRESENT KRENGE?
Graph questions mein generally do type ke graphs milenge:
1. **Directed** (Ek tarfa raasta) vs **Undirected** (Dono taraf raasta)
2. **Weighted** (Raaste ki cost) vs **Unweighted** (Cost nahi hai)

Par in sabko code mein utaarne ke liye (ya question mein kaise diya hoga), humare paas mainly **3 Forms of Graph Representation** hoti hain:

---

### 1️⃣ ADJACENCY MATRIX (The Basic but Space Heavy Approach)
*Adjacency Matrix ek 2D Vector ya 2D Array hoti hai.*

**Concept:**
Hum ek `N x N` ka 2D vector banate hain. Agar Node `u` se Node `v` tak edge hai, toh hum `matrix[u][v] = 1` kar dete hain, varna `0` rakhte hain. (Agar weighted hai toh `1` ki jagah weight daal dete hain).

```cpp
// N is the number of nodes
vector<vector<int>> matrix(n, vector<int>(n, 0)); 
matrix[u][v] = 1; // Edge from u to v
```



**SC (Space Complexity) = O(N^2)**

- **Kyu itni gandi Space Complexity?** Dikkat yeh hai ki bhale hi Node `0` aur Node `2` ke beech mein _koi edge na ho_, fir bhi humein us cell ko `0` se fill toh karna padega na! Hum poora `N x N` ka dabba bana rahe hain memory mein. So basic old maths bro: `N x N` 2D matrix ka SC hamesha `O(N^2)` hota hai.
- **Ye kyu nahi pasand karte hum?** Because of this bad SC. Agar `10^5` nodes hue, toh matrix ban hi nahi payegi (Memory Limit Exceeded).
- **Kab use karna hai?** Bahut rare. Sirf tab jab nodes bahut kam ho (e.g., `N <= 1000`) aur tumhe `O(1)` time mein direct check karna ho ki `u` se `v` ki edge hai ya nahi




### 2️⃣ ADJACENCY LIST (Asli Maal / Most Used)

_Yeh sabse zyada use hone wala aur optimized tareeka hai boss._

**Concept:** Hum ek vector banate hain, aur uske har index par ek aur vector (list) rakhte hain jo sirf aur sirf un nodes ko store karega jinse actually connection hai. Nothing extra!

```

vector<vector<int>> adj(n); // Vector of vectors
// OR
vector<int> adj[n];         // Array of vectors

adj[u].push_back(v);        // Directed edge u -> v
// adj[v].push_back(u);     // Add this line if Undirected

```



- **Ab pagal ke jaise mat puchna kaise be!** Intuition samjho:
    1. Tune `N` size ka ek vector (outer list) declare kiya `(0 to N-1)`. Yeh memory lega **`O(N)`**.
    2. Har node ke paas alag number of edges hongi (kisi ke paas 3, kisi ke paas 1, kisi ke paas 0). Har location is storing a vector, par uska size you don't know yet.
    3. Par itna toh sure hai ki total graph mein Edges **`E`** hi hain. Toh saare nodes ke internal elements mila ke exactly `E` elements hi store honge.
- So, Fixed space `O(N)` + Extra Added Space `O(E)` = **`O(N + E)`**. Yahan matrix ki tarah space waste nahi ho raha.



### 3️⃣ GRID (The Implicit Graph)

_Yahan direct graph nahi diya hota, balki ek 2D Grid diya hota hai boss._

**Concept:** Grid ka har ek cell `(r, c)` apne aap mein ek Node (vertex) hai.  
Aur uske valid neighbors (Up, Down, Left, Right) uski edges hain.

**SC (Space Complexity) = O(1) (Extra Space for Graph)**

- **Kyu?** Us grid ke cell values nikal ke tum custom Nodes bana sakte ho par **WHY TO DO THAT?** Sara kaam direct grid mein traversal karke karo be! Faltu mein Adjacency List banakar Space aur Time Complexity badhane ki zarurat nahi hai.
- Implicit graph ka rule: Jo input diya hai, usi ke upar algorithm lagao.

Grid (`vector<vector<int>> grid`) khud ek **Implicit Graph** (Chhupa hua graph) hai.

Yahan koi node `0, 1, 2` nahi hota. Yahan node ka naam uski location hoti hai: `(r, c)`.

**Grid ka Khel:**

* **Node** = Ek single cell `(r, c)`.

* **Edge** = Us cell ke chaaro taraf ke cells (Up, Down, Left, Right).

* Jab tum ek cell se dusre cell mein jaate ho, woh exactly ek node se uske neighbor node pe jaane jaisa hi hai.


**Grid ko Traverse Kaise Karte Hain? (Short Snippet):**

Humein kisi Adj List ki zarurat nahi. Hum direction arrays (`dr`, `dc`) use karke neighbors nikalte hain.

```cpp

int dr[] = {-1, 1, 0, 0}; // Up, Down

int dc[] = {0, 0, -1, 1}; // Left, Right

// Current node is (r, c)

for (int k = 0; k < 4; k++) {

    int nr = r + dr[k]; // Neighbor Row

    int nc = c + dc[k]; // Neighbor Col

    // Boundary check + Valid check

    if (nr >= 0 && nr < ROWS && nc >= 0 && nc < COLS && grid[nr][nc] == 1) {

        // Yeh cell humara valid edge/neighbor hai! Isme ghus jao

        dfs(nr, nc, grid); 

    }

}
```




## 🔄 3. GRID KO KAB CONVERT KARNA PAD SAKTA HAI? (Aur Kyu?)

Maine bola tha 99% questions mein direct Grid traversal chalta hai. Toh wo **1% questions kaunse hain jahan Grid ko 1D Node ya Adj List mein convert karna padta hai?**

**When & Why:** Jab humein DSU (Disjoint Set Union) ya Kruskal's jaisa koi special data structure lagana ho, toh wo algorithms 1D arrays (`parent[]`, `size[]`) use karte hain. Un algorithms ko `(r, c)` jaise 2D coordinates samajh nahi aate. Unko single number chahiye: `0, 1, 2, 3...`

**Conversion Formula (2D to 1D):** Grid ke kisi bhi `(r, c)` cell ko ek unique single number (node ID) mein badalne ka ek standard mathematical formula hota hai: `Node_ID = (r * total_columns) + c`

_Example:_ `3x3` grid hai. Agar tum row 1, col 2 `(1,2)` par ho: `Node ID = (1 * 3) + 2 = 5`. Toh wo cell graph ka "Node 5" ban gaya. Ab is Node 5 ko list mein daal lo!



## 🤔 1. Adjacency Matrix O(1) mein kaise kaam karti hai? (Aur N <= 1000 kyu?)

Tune pucha "How is this possible?" Dekh bhai, Matrix kuch nahi bas ek 2D Array hai.

**O(1) Edge Check Logic:**

Agar main tujhse puchu: "Kya Node 3 se Node 5 tak rasta hai?"

* **Adjacency List mein:** Tujhe `adj[3]` ke andar ghus kar poori list mein loop lagana padega dhoondhne ke liye ki `5` hai ya nahi. Yeh `O(Edges of Node 3)` time lega.

* **Adjacency Matrix mein:** Tu seedha memory location hit karega `if(matrix[3][5] == 1)`. Array ka index look-up hamesha **O(1)** time leta hai. Khataak se answer mil jayega!

**Lekin sirf N <= 1000 kyu?**

Memory Limit Exceeded (MLE) ka darr!

* Agar `N = 1000` hai, toh `1000 x 1000 = 10^6` elements. Yeh bas 4 MB memory lega (Aaram se pass).

* Lekin agar `N = 10^5` (jo normal graph questions mein hota hai) hua, toh `10^5 x 10^5 = 10^10` elements. Iske liye kareeb **40 GB RAM** chahiye! Leetcode ka server phatt jayega. Isliye matrix ko tabhi chuna jata hai jab N chhota ho.





