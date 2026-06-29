

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

