# Linked List

## Core Idea

Linked list problems are mostly:

```text
pointer rewiring
```

The difficult part is:
- not losing nodes
- changing connections safely

---

## Important Insight

Singly linked lists only move forward.

This makes reversing difficult because:

```text
we must reconnect pointers manually
```

---

## Dummy Node

Dummy node simplifies:
- head deletion
- insertion
- merge operations

Example:

```java
ListNode dummy = new ListNode(-1);
dummy.next = head;
```

Key idea:
Treat head like a normal node.

---

## Reverse Linked List II

The hardest part is not reversing values.

The hardest part is:

```text
reconnecting pointers correctly
```

Important:
- save next pointer first
- move nodes carefully
- think locally, not globally

---

## Common Pointer Pattern

```java
next = curr.next;
curr.next = prev;
```

Always save next node before rewiring.

---

## My Learning Notes

At first, I tried to mentally reverse the whole list.

That made everything confusing.

Now I focus on:

```text
changing one pointer at a time
```

This makes linked list problems much clearer.