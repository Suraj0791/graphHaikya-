

DFS cannot escape a subtree until the subtree is completely explored.

That sentence is the seed from which the entire Euler Tour Bible grows.


# The Big Realization

Every subtree behaves like a **time bubble**

Enter B

┌────────────────────┐

Everything inside B

must happen here

└────────────────────┘

Exit B



Nothing outside B can interrupt that interval (in a tree).

Everything in B's subtree lives completely inside B's lifetime.

That means...

A subtree is not just a graph structure anymore.

It is also a **continuous interval in time**.

This is the first major law of the DFS Time Family.



# The Central Mystery of the Euler Tour Bible

By the end of this Bible, you'll answer one question:

> **How can a tree magically become an array while preserving every subtree?**

That sounds impossible today.

By the end, it will feel inevitable.


> **DFS doesn't just visit nodes—it creates a timeline. Every subtree occupies one continuous interval on that timeline. Euler Tour is simply the act of recording that hidden timeline.**





# Imagine You're Watching DFS Live

Take this tree.

```
        A
      / | \
     B  C  D
    / \
   E   F
```

Now become DFS.

Not programmer.

Become DFS.



# Every Event Has an Order

Let's write them.

```
1. Enter A
2. Enter B
3. Enter E
4. Exit E
5. Enter F
6. Exit F
7. Exit B
8. Enter C
9. Exit C
10. Enter D
11. Exit D
12. Exit A
```



Why did we write numbers?

Because...

events happen one after another.

Exactly like seconds on a clock.




# Now Look Carefully

Let's record both events for every node.

| Node | Enter | Exit |
| ---- | ----- | ---- |
| A    | 0     | 11   |
| B    | 1     | 6    |
| E    | 2     | 3    |
| F    | 4     | 5    |
| C    | 7     | 8    |
| D    | 9     | 10   |
|      |       |      |
|      |       |      |


Notice what's happening.

The bigger the subtree...

the longer it stays alive.



# Here's the Crazy Observation

Look again.

|Node|Lifetime|
|---|---|
|A|0 → 11|
|B|1 → 6|
|E|2 → 3|
|F|4 → 5|
```
Time →

0                     11
A ───────────────────────

   1          6
   B ───────────

      2  3
      E ──

          4 5
          F ──
```



Do you notice?

They're not random.

They're nested.

Like Russian dolls.



# Chapter 2 — Why Every Subtree Becomes One Continuous Interval




**Why is B one continuous interval?**

Why not

```
1 -- 3...7 -- 9
```

Why doesn't B's subtree get split?

Who guarantees this?

Once DFS enters a node...

it becomes trapped inside that node's subtree.

Imagine B creates a room.




Enter B

┌─────────────────────────┐

Everything inside B

must happen here

└─────────────────────────┘

Exit B




DFS cannot teleport.

The only exit from the room...

is

```
Exit B
```

Until then...

everything that happens belongs to B.



# DFS Has No Choice

This is the important sentence.

> **DFS does not choose to finish a subtree continuously.**
> 
> **The tree forces it to.**

Read that again.

Euler Tour is not clever.

It is inevitable.




# This Is the Law



┌───────────────────────────────┐

A

     ┌───────────────┐

     B

          ┌─────┐

          E

          └─────┘

     └───────────────┘

└───────────────────────────────┘



Notice.

Bubbles never partially overlap.

They either

contain

or

are disjoint.

Exactly like tree subtrees



# Why Partial Overlap Is Impossible



Suppose someone claims

B

┌───────────────┐

        C

     ┌──────────────┐

└───────────────┘

      └──────────────┘

Partial overlap.

Can this happen?

No.

Why?

Because then DFS would have to
leave B
enter C
come back to B
without exiting B.
Impossible.The recursion stack doesn't allow it.





# his Is Why Euler Tour Exists

The clock is only recording something deeper.

The deeper truth is

```
Recursion

↓

Creates nested execution

↓

Nested execution

↓

Creates nested intervals

↓

Clock records intervals


# The Stack Explains Everything

Remember DFS recursion?

```
dfs(B){    dfs(E);    dfs(F);}
```

Question.

Can execution leave

```
dfs(B)
```

before

```
dfs(F)
```

finishes?

Impossible.

Why?

Because

`dfs(B)` is still on the call stack.

This is HUGE.

The call stack itself enforces the interval.

Not Euler.

Not timestamps.

The recursion stack


```

The timer didn't create intervals.

The recursion did.

The timer simply took photographs.



# The Deepest Mental Model So Far

Imagine every recursive DFS call opens a bracket.

```
dfs(A)(
```



Then

```
dfs(B)
(
```

Then



```
dfs(E)()
```

Back.

Then

```
dfs(F)()
```

Back.



(

    (

        ()

        ()

    )

    ()

)



# The Most Important Law of Euler Tour

> **Between `Enter(u)` and `Exit(u)`, DFS is physically incapable of visiting anything outside `u`'s subtree.**

Everything else in Euler Tour is a consequence of this one law.

Ancestor checks.

Subtree queries.

Tree flattening.

Segment trees.

LCA preprocessing.

All of them.



A DFS call is like opening a parenthesis. It cannot close until every recursive child call finishes. Therefore every subtree forms one perfectly nested, continuous interval on the DFS timeline. The timer merely records those parentheses.



# Combine Both Laws

Parent starts first.

Parent finishes last.

Draw them.



Time →

1                     6
B ───────────────────────

     2      3
     E ───────



Now read left to right.

```
Enter(B)↓Enter(E)↓Exit(E)↓Exit(B)
```

That becomes



tin(B)

<

tin(E)

<

tout(E)

<

tout(B)



tin[u]

<

tin[v]

<

tout[v]

<

tout[u]





# Let's Compress Everything

## Law 1

Parent enters first.

```
tin[parent]<tin[child]
```

---

## Law 2

Parent exits last.

```
tout[parent]>tout[child]
```

---

## Law 3

Siblings never overlap.

Intervals are disjoint.

---

Together they become

```
Intervals either
Contain
or


Are Disjoint
```

Exactly like subtrees.


The tree has become geometry.

Ancestor becomes

Containment.

Sibling becomes

Disjoint intervals.

Children become

Nested intervals.

The graph has transformed into mathematics.




A

┌────────────────────┐

    B

    ┌──────────┐

        E

        ┌──┐

        └──┘

        F

        ┌──┐

        └──┘

    └──────────┘

    C

    ┌──┐

    └──┘

└────────────────────┘




# The Hidden Superpower

Imagine I erase the tree.

I only give you this.



A

0 ----------- 15

B

1 ------ 8

C

9 -----14

E

2 --3

F

4 --7




Question.

Can you reconstruct relationships?

Yes.

You don't need edges anymore.

Intervals contain enough information.

This is insane.

We've encoded the tree into time.




# Why This Matters

Every future algorithm will stop thinking about

```
NodesEdges
```

Instead it will think

```
IntervalsRanges
```

That's why segment trees work.

That's why Fenwick trees work.

That's why subtree queries become array queries.

You're no longer solving graph problems.

You're solving range problems.



# he One Formula Everyone Memorizes

Most books write

```
if (tin[u] <= tin[v] &&    tout[v] <= tout[u])
```

and say

> "This checks whether u is ancestor of v."

Students memorize it.

You shouldn't.

Because this formula is just a direct consequence of the interval containment law.

If `u`'s interval contains `v`'s interval, then `u` must have entered first and exited last.





# Chapter 4 — Ancestor Queries Without Traversing the Tree

---

> **This is the first moment where Euler Tour feels like magic.**
> 
> But by the end of this chapter you'll realize...
> 
> **It isn't magic.**
> 
> It's just geometry.



# The Old World

Suppose I ask

> **Is B an ancestor of F?**

Before Euler Tour...

what would you do?

Probably DFS.



Worst case?

You explore the subtree.

Time:

```
O(Size of subtree)
```

Or even

```
O(N)
```

depending on implementation



# Imagine an Interview

Interviewer asks.

> I will ask you one million ancestor queries.

```
Is A ancestor of X?Is D ancestor of Y?Is C ancestor of Z?...
```

Would you run DFS every time?

Impossible.

There must be a smarter way.



# Our New Weapon

We already computed

|Node|tin|tout|
|---|---|---|
|A|0|11|
|B|1|6|
|E|2|3|
|F|4|5|
|C|7|8|
|D|9|10|

The tree is gone.

Only numbers remain.

Question.

Can these numbers answer everything?



# Example 1

Is B ancestor of F?

Forget the tree.

Look only here.



B

1 ---------- 6

F

    4 --- 5




Question.

Where is F?

Inside B.

Immediately obvious.

Because

```
1 <= 4and5 <= 6
```

Done.

No traversal.




# Wait...

We never used the tree.

Not once.

Only intervals.

---




# Let's Derive the Rule

Suppose

u

is ancestor of

v.

We proved in Chapter 3

```
tin[u]<tin[v]<tout[v]<tout[u]
```

Ignore strict vs non-strict.

Focus on containment.




How do we mathematically express

"u contains v"?

Exactly.

Two conditions.

---

## Condition 1

u starts before v.

```
tin[u]<=tin[v]
```

---

## Condition 2

u ends after v.

```
tout[v]<=tout[u]
```

Both true?

Then

v

is inside u.

That's it.




A

┌─────────────────────────────┐

     B

     ┌──────────────┐

         E

         ┌─────┐

         └─────┘

     └──────────────┘

└─────────────────────────────┘




Question.

How do you know

E is inside B?

Geometry.

Not graphs.

Exactly the same thing





# This Is The Real Compression

Originally

```
Graph↓DFS↓Find ancestor
```

Now

```
Numbers
↓
Two comparisons
↓


Answer
```

Think about how insane that is.

We replaced graph traversal with

```
4 integers.
```




New way.

```
if (tin[u] <= tin[v] &&    tout[v] <= tout[u])
```

Time

```
O(1)
```

No recursion.

No graph.

No traversal.

Just comparisons.



# But Wait...

Who Paid the Cost?

Nothing is free.

Somebody paid.

Who?

DFS.

The initial Euler Tour.

It computed

```
tintout
```

once.

Time

```
O(N)
```

After that...

millions of ancestor queries become

```
O(1)
```

Classic preprocessing tradeoff.





# This Pattern Appears Everywhere

Notice something.

We keep seeing this in algorithms.

---

## Prefix Sum

Pay once.

```
O(N)
```

Answer

```
Range Sum↓O(1)
```




# The Deeper Truth

We thought

```
Ancestor=Graph property
```

Wrong.

It is actually

```
Ancestor=Interval containment
```

The graph was just one representation.

Euler Tour found a better one.





An ancestor is simply a node whose DFS lifetime completely contains another node's lifetime. After Euler preprocessing, ancestor queries are no longer graph problems—they become interval containment problems solved with two comparisons.



Right now we can answer:

- ✅ Ancestor queries
- ✅ Descendant queries

But remember the promise from Chapter 0?

> **How can a tree magically become an array?**

We haven't answered that yet.

In fact, something still seems impossible.




So far we've used **entry and exit timestamps** (`tin` and `tout`) where the timer increments on both enter and exit. This is perfect for understanding **interval containment** and ancestor checks.

However, when we move to **tree flattening** in the next chapter, many implementations switch to a slightly different Euler numbering (recording nodes on entry and using subtree sizes, or recording the Euler order array). That's **not a contradiction**—it's a different way of encoding the same DFS interval idea, optimized for range queries.




# 📖 EULER TOUR BIBLE

# Chapter 5 — How a Tree Magically Becomes an Array

---




# The Promise We Made

Back in Chapter 0, I asked a crazy question.

> **Can we turn this...**

```
        A
      /   \
     B     C
    / \
   E   F
```

> **...into this?**

```
[ ?, ?, ?, ?, ?, ? ]
```

Without losing subtree information.

At first, this seems impossible.

A tree is 2-dimensional.

An array is 1-dimensional.

How can one represent the other?

Imagine the tree contains values.


        A(5)
      /      \
   B(2)      C(7)
   /   \
E(1)   F(3)




Now suppose I ask:

> **Find the sum of B's subtree.**

Answer:

```
B + E + F=2 + 1 + 3 = 6
```

Easy.

---

Now suppose I ask this **100,000 times**.

Different subtrees.

Different updates.

Different queries.

Would you run DFS every time?



```
Query  ->  DFS  -> Visit subtree  ->  Answer
```

Time:

```
O(Size of subtree)
```

Too slow.



# We Need a Better Representation

Suppose...

just suppose...

B's subtree could somehow become

```
[2,1,3]
```

inside an array.

Then

Subtree Sum

would become

Range Sum.

Suddenly we can use

- Prefix Sum
- Fenwick Tree
- Segment Tree

Wait...

That's exactly what we want.




# The Impossible Requirement

We need an array where

```
Subtree↓Continuous Segment
```

Not scattered.

Continuous.

Question.

Can DFS accidentally do this?




# Let's Record ONLY Entry

Forget exit time for a moment.

Imagine every time DFS ENTERS a node...

we write it into an array.



        A
      /   \
     B     C
    / \
   E   F



Now record entry.

```
ABEFC
```

Array becomes

```
Index0  1  2  3  4ValueA  B  E  F  C
```

Pause.

Just stare.




Where are B's subtree nodes?

```
A[B E F]C
```

Wait...

They're together.

Interesting.



# Why Does This Happen?

Think back to Chapter 2.

What was our biggest law?

> **DFS cannot leave a subtree until it completely finishes it.**

Now let's replay the DFS.

```
Enter B↓Record B↓Enter E↓Record E↓Finish E↓Enter F↓Record F↓Finish F↓Exit B
```

Question.

Could C get recorded here?

```
BECF
```

Impossible.

Why?

Because DFS hasn't exited B.

Exactly!




# The Key Insight

When we record **only ENTRY events**...

DFS writes

```
Node↓All descendants↓Exit
```

Since DFS cannot escape the subtree...

every descendant gets recorded immediately after its parent.

Nothing from outside can interrupt.




Notice.

Everything belonging to B got written

before anything outside B.

That means

B's subtree occupies

one continuous block.



# This Is NOT Because of Arrays

The array is innocent.

The real reason is still

the recursion stack.




This process is called

```
Tree Flattening
```

or

```
Euler Flattening
```

