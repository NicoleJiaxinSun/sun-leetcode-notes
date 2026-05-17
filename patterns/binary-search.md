# Binary Search

## Core Idea
Binary search is not just to "find a number".
The core idea is shrinking the search space.
---

## Two Main Templates

### Exact Search

```java
while(left <= right)
```

Use when:
- searching exact target
- checking if target exists

Key:
- must exclude mid
- left = mid + 1
- right = mid - 1

Reason:
mid has already been checked.

---

### Boundary Search

```java
while(left < right)
```

Use when:
- finding minimum
- finding peak
- finding first/last position
- finding boundary

Key:
- sometimes keep mid

Usually:

```java
right = mid;
```

or

```java
left = mid + 1;
```

Reason:
mid may still be the answer.

---

## Important Insight

The hardest part of binary search is not calculating mid.

The hardest part is:
- deciding whether to keep or exclude mid
- understanding what left/right represent
- understanding the meaning of the final pointer

---

## Mental Model

Ask:

```text
Which side is definitely impossible?
```

Remove only the impossible side.

---

## Infinite Loop Warning

This causes infinite loop:

```java
left = mid;
```

when using:

```java
while(left < right)
```

because mid may equal left.

Fix:

```java
left = mid + 1;
```

---

## My Learning Notes

I used to mix:
- exact search
- boundary search

Now I understand they are different problems with different templates.

Boundary search usually keeps candidates alive.

Exact search removes checked candidates immediately.