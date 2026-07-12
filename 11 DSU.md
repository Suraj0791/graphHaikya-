

```
void unite(int a,int b){

    a=find(a);
    b=find(b);

    if(a==b)
        return;

    if(rank[a]<rank[b])
        swap(a,b);

    parent[b]=a;

    if(rank[a]==rank[b])
        rank[a]++;
}


int find(int x){

    if(parent[x]==x)
        return x;

    return parent[x]=find(parent[x]);
}

vector<int> parent;
vector<int> rank;

void make(int n){

    parent.resize(n);

    rank.assign(n,0);

    for(int i=0;i<n;i++)
        parent[i]=i;
}
```




Cycle Detection

Process edges.

If

```
find(u)==find(v)
```

Cycle.

Otherwise

Union.

This is the simplest use of DSU.





## Pattern 4

Offline Connectivity

Edges added later.

Queries mixed.

Reverse processing.

DSU shines.

(We'll learn this properly when doing offline algorithms





## Pattern 5

Grid → DSU

Treat every cell

as

```
Node
```

Union neighbours.

Problems

- Number of Islands II
- Making Large Island
- Regions Cut by Slashes

This is where people realize

DSU isn't only for normal graphs


