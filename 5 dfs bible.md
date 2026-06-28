


# FIRST PRINCIPLE

DFS is **not an algorithm.**

DFS is a behavior.

The behavior is

> "Whenever I choose a path,  
> I keep following that path  
> until I absolutely cannot continue."

That's it.

Everything else comes later.



DFS has one soul sentence:

> **"Finish one path completely before giving attention to another."**

Everything in DFS comes from this.

Not recursion.
Not stack.
Not trees.
Not graphs.



People say
> "DFS uses recursion.

Wrong.

People say

> "DFS uses a stack."
Still backwards.



The truth is

> **DFS creates a problem.**
> **The stack is simply the only thing that can solve that problem.**

Exactly like BFS.
Nobody invented the queue first and then BFS.
The exploration strategy demanded a queue.


DFS is

**the exploration strategy.**
Recursion is
**one implementation.**
Stack is
**the mechanism.**
Three completely different things.



# Mental Models You Should Carry Forever

1. **Breadcrumbs in a cave** — every step in, drop one; every step out, pick up the latest.
2. **Nested folders** — finish the deepest folder before returning.
3. **Browser Back button** — you always return to the most recently opened page.
4. **Promises** — the stack stores unfinished promises, not completed history.
5. **Paused work** — a stack frame is a frozen snapshot of what remains to be done.
