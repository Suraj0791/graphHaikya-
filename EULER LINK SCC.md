

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